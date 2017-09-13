React & Redux Tips
----------------

React & Redux やそれに付随するフロントエンド技術に関するメモ。


### React

* [React でフォームのイベントハンドラをどう扱うか](how-to-deal-with-form-components.md)
* [Extracting Logic from React Components](https://javascriptplayground.com/blog/2017/07/react-extracting-logic/)
    * React コンポーネントからどのようにロジックを分離するか
    * 関数に分離してテスト書く、という当たり前といえば当たり前の話
    * [サンプルリポジトリ](https://github.com/javascript-playground/react-refactoring-with-tests) の構成などは参考になる

### Redux

* [The Redux ecosystem — Medium](https://medium.com/@denisraslov/the-redux-ecosystem-539c630ec521#.6bsqgqpf7)
* [Reselect tutorial. Optimizing React Redux application development with Reselect. | Codebrahma](https://codebrahma.com/reselect-tutorial-optimizing-react-redux-application-development-with-reselect/)
    * Reselect の概要とサンプルコード。チュートリアルと言いつつサンプルコードは断片的で手を動かして学ぶようにはできていない
* [A small trick to write clean reducers – Hacker Noon](https://hackernoon.com/a-small-trick-to-write-clean-reducers-a0b1b1eff3d2)
    * 深いネスト構造になってしまった state の一部を更新するためのシンプルな書き方について
    * [lodash/fp](https://github.com/lodash/lodash/wiki/FP-Guide) を使うと Immutable に更新できていいですよ、という話

```javascript
import set from 'lodash/fp/set';

const store = createStore((state = {repoIds, reposById}, action) => {
  switch (action.type) {
  case UPDATE_TAG:
    return set('reposById.1.tags[0]', {id: 213, text: 'Node.js'}, state);
  default:
    return state;
  }
})
```
