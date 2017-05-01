---
layout: post
title: Linked List (연결 리스트)
date: 2017-04-30 01:00:00
categories: [개발이야기]
tags: [LINKED LIST, 연결 리스트, JS, JAVASCRIPT, 자바스크립트]
image: /assets/images/2017-04-30-linked-list/desktop.png
image2: /assets/images/2017-04-30-linked-list/mobile.png
---

###### 연결 리스트 실 사용 예제를 소개합니다.

###### 테스트 하기

예제를 실행하면 우측 상단에 아래의 버튼들이 있습니다.

- addListener (리스너 등록)
- removeListener (리스너 삭제)
- displayListeners (남아 있는 리스너 보기, 오류 있슴)
- changeUpdate (업데이트 함수 변경, 토글)

###### addListener

클릭하면 Listener를 등록하고 등록된 Listener의 tick 함수가 호출되며 duration 이후 종료합니다.

###### changeUpdate

update 함수를 토글합니다. {true: 패딩과 함께 업데이트, false: 패딩 없이 업데이트}

###### 패딩 없이 업데이트하는 경우

패딩 없이 업데이트하면 마지막에 등록된 Listener의 tick 함수는 호출하지 않습니다.

###### 호출하지 않는 이유

아래에 연결 리스트 생성 과정과 호출 순서를 표로 작성하였습니다

[패딩이 없는 경우 update 함수 호출 순서](###### 패딩이 없는 경우 update 함수 호출 순서) 를 참고하세요.

###### _tickerListenerPaddings 생성과 연결 상태

| 생성 순서 | nextListener | prevListener |
| ----- | ------------ | ------------ |
| [0]   | 1            | null         |
| [1]   | 2            | 0            |
| [2]   | 3            | 1            |
| [n]   | n + 1        | n - 1        |
| [9]   | null         | 8            |

###### addListener 호출 시 연결 상태

| _numListeners | in _first | nextListener | prevListener | out _first |
| ------------- | --------- | ------------ | ------------ | ---------- |
| 0             | null      | null         | 1            | 0          |
| 1             | 0         | 0            | 2            | 1          |
| 2             | 1         | 1            | 3            | 2          |
| 3             | 2         | 2            | null         | 3          |

###### 패딩이 있는 경우 update 함수 호출 순서 

| listener id | nextListener | prevListener |
| ----------- | ------------ | ------------ |
| padding     | 3            | null         |
| 3           | 2            | padding      |
| 2           | 1            | 3            |
| 1           | 0            | 2            |
| 0           | null         | 1            |

###### 패딩이 없는 경우 update 함수 호출 순서

| listener id | nextListener | prevListener |
| ----------- | ------------ | ------------ |
| 3           | 2            | null         |
| 2           | 1            | 3            |
| 1           | 0            | 2            |
| 0           | null         | 1            |

패딩이 없으면 마지막에 등록된 리스너의 tick 함수는 호출되지 않습니다.

###### [JavaScript][jsfiddle]

```javascript
// requestAnim shim layer by Paul Irish
window.requestAnimFrame = (function() {
  return window.requestAnimationFrame ||
    window.webkitRequestAnimationFrame ||
    window.mozRequestAnimationFrame ||
    window.oRequestAnimationFrame ||
    window.msRequestAnimationFrame ||
    function( /* function */ callback, /* DOMElement */ element) {
      window.setTimeout(callback, 1000 / 60);
    };
})();


onload = test;

// 테스트 시작
function test() {
  var test = new Test();
}


var p;

/**
 * Listener 클래스
 */
function Listener(listenerEndCount) {
  this.id = window.listenerId++;
  this.tickCount = 0;
  this.listenerEndCount = listenerEndCount || (100 + parseInt(Math.random() * 200));
  this.prevListener = null;
  this.nextListener = null;
  echo('id: ' + this.id + ', listenerEndCount:' + this.listenerEndCount);
}

p = Listener.prototype;

/**
 * tick 함수 반환 값이 true 이면 연결 리스트에서 제거 합니다.
 * @returns {boolean}
 */
p.tick = function() {
  if (this.listenerEndCount == -1) return false;

  echo(this.id + ' -> ' + this.tickCount + ', ' + this.listenerEndCount);
  if (this.tickCount++ >= this.listenerEndCount) {
    echo('id: ' + this.id + ' end');
    return true;
  }
  return false;
}


/**
 * 테스트 클래스
 */
function Test() {
  this.initialize();
  this.initializeGUI();
  this.render();
}


var p = Test.prototype;


p.initialize = function() {
  // TEST ID
  window.listenerId = 0;

  this._first = null;
  this._listeners = [];
  this._numListeners = 0;
  this._tickerListenerPaddings = [];

  var prevListener = null;

  for (var i = 0; i < 10; ++i) {
    var listener = new Listener(-1);
    if (prevListener != null) {
      prevListener.nextListener = listener;
      listener.prevListener = prevListener;
    }
    prevListener = listener;
    this._tickerListenerPaddings[i] = listener;
  }

  this.changeUpdateMethode(true);
};

p.initializeGUI = function() {
  this.gui = new dat.GUI();

  this.config = {};
  this.config.addListener = this.testAddListener.bind(this);
  this.config.removeListener = this.testRemoveListener.bind(this);
  this.config.displayListeners = this.displayListeners.bind(this);
  this.config.changeUpdate = this.toggleUpdateFunction.bind(this);

  this.gui.add(this.config, 'addListener');
  this.gui.add(this.config, 'removeListener');
  this.gui.add(this.config, 'displayListeners');
  this.gui.add(this.config, 'changeUpdate');
}

p.testAddListener = function() {
  var listener = new Listener();
  echo('\ntestAddListener( ' + listener.id + ' )');

  this._listeners.push(listener);

  this.addListener(listener);
}

p.testRemoveListener = function() {
  if (this._listeners.length <= 0) return;

  var listener = this._listeners.pop();
  echo('\ntestRmoveListener( ' + listener.id + ' )');

  this.removeListener(listener);
}

p.displayListeners = function() {
  var total = this._listeners.length;
  echo('total listeners: ' + total);
  for (var i = 0; i < total; i++) {
    var listener = this._listeners[i];
    echo(listener.id);
  }
}

p.toggleUpdateFunction = function() {
  this.changeUpdateMethode(!this.widthPadding);
}

/**
 * 업데이트 함수 변경
 * {true: 패딩과 함께 업데이트, fals: 패딩 없이 업데이트}
 */
p.changeUpdateMethode = function(withPadding) {
  echo('changeUpdate( ' + withPadding + ' ), option: ' + ((withPadding) ? 'widthPadding' : 'widthOutPadding'));
  this.widthPadding = withPadding;

  if (this.widthPadding) {
    this.update = this.updateWithPadding.bind(this);
  } else {
    this.update = this.updateWithOutPadding.bind(this);
  }
}

/**
 * 리스너 등록
 * @param listener {Listener}
 * 등록시 연결 리스트 관계 참고
 * https://github.com/twipixel/be/blob/master/test/linked/README.md
 */
p.addListener = function(listener) {
  if (listener.nextListener != null || listener.prevListener != null) {
    return;
  }

  echo('** addListener( ' + listener.id + ' ), numListeners: ' + this._numListeners);

  if (this._first != null) {
    listener.nextListener = this._first;
    this._first.prevListener = listener;
  }

  this._first = listener;

  ++this._numListeners;
}

/**
 * 리스너 삭제
 * @param listener {Listener}
 */
p.removeListener = function(listener) {
  echo('** removeListener( ' + listener.id + ' ), numListeners: ' + this._numListeners);

  var l = this._first;

  while (l != null) {

    if (l == listener) {
      if (l.prevListener != null) {
        l.prevListener.nextListener = l.nextListener;
        l.nextListener = null;
      } else {
        this._first = l.nextListener;
      }
      if (l.nextListener != null) {
        l.nextListener.prevListener = l.prevListener;
        l.prevListener = null;
      }
      --this._numListeners;
    }

    l = l.nextListener;
  }
}

/**
 * Test Code
 * 디버그를 위한 코드
 * @param listener
 */
p.removeFromListeners = function(listener) {
  var total = this._listeners.length;

  for (var i = 0; i < total; i++) {
    var l = this._listeners[i];

    if (l === listener) {
      this._listeners.splice(i, 1);
    }
  }
}

/**
 * 패딩과 함께 업데이트 하기
 * 패딩이 있어야 Listener 의 모든 tick 함수를 호출할 수 있습니다.
 *
 * 호출 관계 참고
 * https://github.com/twipixel/be/blob/master/test/linked/README.md
 */
p.updateWithPadding = function() {
  var n = 8 - (this._numListeners % 8),
    listener = this._tickerListenerPaddings[0],
    l = this._tickerListenerPaddings[n],
    ll = null;

  // 진입점에 _first 를 연결합니다.
  if ((l.nextListener = this._first) != null) {
    this._first.prevListener = l;
  }

  // entry 에 연결된 연결 리스트 체인 실행
  while (listener.nextListener != null) {
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
    if ((listener = listener.nextListener).tick()) {
      // Test Code
      this.removeFromListeners(listener);

      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;
      --this._numListeners;
    }
  }

  // _first prev 초기화 null 셋팅
  if ((this._first = l.nextListener) != null) {
    this._first.prevListener = null;
  }

  // padding 순환 고리 설정
  l.nextListener = this._tickerListenerPaddings[n + 1];
}

/**
 * 패딩 없이 업데이트 하기
 * 패딩이 없는 경우 마지막에 등록된 Listener 는 호출되지 않습니다.
 *
 * 호출 관계 참고
 * https://github.com/twipixel/be/blob/master/test/linked/README.md
 */
p.updateWithOutPadding = function() {
  var listener = this._first,
    ll = null;

  while (listener && listener.nextListener != null) {

    // 리스너 tick 함수가 true 를 리턴하면 제거합니다.
    if ((listener = listener.nextListener).tick()) {

      // 리스트 연결
      if (listener.prevListener != null) {
        listener.prevListener.nextListener = listener.nextListener;
      }
      if (listener.nextListener != null) {
        listener.nextListener.prevListener = listener.prevListener;
      }

      // 리스트 삭제
      ll = listener.prevListener;
      listener.nextListener = null;
      listener.prevListener = null;
      listener = ll;

      // 리스너 카운트 줄임
      --this._numListeners;

      // Test Code
      this.removeFromListeners(listener);
    }
  }
}

p.render = function(ms) {
  this.update(ms);
  this.requestId = requestAnimationFrame(this.render.bind(this));
}

/**
 * console.log 출력
 */
function echo(message) {
  console.log(message);
  var div = document.createElement('div');
  document.body.appendChild(div);
  div.innerHTML = message;
}
```

---

###### IMAGE

- [Markus Spiske][image-from]


[image-from]: https://unsplash.com/search/hand?photo=nvKQ1kxheRc
[jsfiddle]: https://jsfiddle.net/twipixel/qxuwepn0