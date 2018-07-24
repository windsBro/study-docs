# react-base

## concepts(概念)

1. jsx
2. rendering element
3. components and props
4. state and lifecycle
5. handling event
6. condition rendering
7. lists and keys
8. forms
9. lifting state up _解除状态_
10. composition vs inheritance

```javascript
import React from 'react'
import './Board.css'

class Board extends React.Component {
    constructor(props){
        super(props)
        this.state ={
            squares:Array(9).fill(null),
            xIsNext:true
        }
    }

    //  函数 渲染函数
    renderSquare(i){
        return <Square vaule= {this.state.squares[i]} test={()=>this.handleClick(i)} />
    }

    handleClick(){

        // 通过新建数组来监听 数组变换 detecting data change
        const squares = this.state.squares.slice()
        if (this.calculateWinner(squares) || squares[i]) {
            return
        }
        squares[i] = this.state.xIsNext ?'X':'O'
        this.setState({
            squares:squares,
            xIsNext:!this.state.xIsNext
        })
    }
    // winner condition
    calculateWinner(squares) {
        const lines = [
            [0, 1, 2],
            [3, 4, 5],
            [6, 7, 8],
            [0, 3, 6],
            [1, 4, 7],
            [2, 5, 8],
            [0, 4, 8],
            [2, 4, 6]
        ]
        for (var i = 0; i < lines.length; i++) {
            const [a,b,c] = lines[i]
            if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
                return squares[a]
                }
            }
        return null;
    }

    render() {
        let status;
        const winner = this.calculateWinner(this.state.squares)
        // let win;
        if (winner) {
            status = 'winner:' + winner
        } else {
            status = 'Next player: ' + (this.state.xIsNext? 'X': 'O');
        }
        return (
            <div>
                <div className="status">{status}</div>
                <div className="board-row">
                    {this.renderSquare(0)}
                    {this.renderSquare(1)}
                    {this.renderSquare(2)}
                </div>
                <div className="board-row">
                    {this.renderSquare(3)}
                    {this.renderSquare(4)}
                    {this.renderSquare(5)}
                </div>
                <div className="board-row">
                    {this.renderSquare(6)}
                    {this.renderSquare(7)}
                    {this.renderSquare(8)}
                </div>
            </div>
        );
    }
}



// square 组件
class Square extends React.Component {
    constructor(props) {
        super(props)
    }

    render(){
        return (
            <button className='square' onClick= {()=>this.props.test()}></button>
        )
    }

}
```

## advanced guides
    1. coding splitting
    2. context
    3. error boundaries
    4. forwarding Resfs
    5. fragements
    6. Higher-order component(**HOC**)


> a highter-order component is a function that takes a component and returns a new component



## react-router-dom


## props-types
```bash
    npm install props-types
```


## React Loadable
