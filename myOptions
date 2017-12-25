/**
 * Created by Admin on 2017/12/23.
 */
import React, { Component } from 'react';
// import _ from 'lodash';
import './App.css';

export default class MyOptionBox extends Component {
    static defaultProps = {
        
    };
    constructor(props){
        super(props);
        this.state = {
            currentSelect: '',
            showOption: false,
        };
    }


    componentDidMount(){

    };
    getOptionVal(e){
        e.stopPropagation();
        console.log(e.currentTarget.dataset.key);
        this.setState({
            showOption: false,
            currentSelect: e.currentTarget.dataset.key
        })
    };
    showOptionList(e){
        e.preventDefault();
        const {showOption} = this.state;
        this.setState({
            showOption: !showOption
        })
    };
    render() {
        let selectBoxStyle = {
            width: "100%",
            height: "40px",
            background: "#ccc",
        };

        let optionBoxStyle = {
            width: "30%",
            height: "40px",
            background: "#ff0",
            position: "relative",
            lineHeight: "40px"
        };

        let optionListStyle = {
            width: "100%",
            // height: "100%",
            position: "absolute",
            top: "40px",
            left: "0",
            listStyle: "none",
            boxShadow: "0px 1px 5px #888888",
            zIndex: '109'
        };
        let optionObj = {
            //这里属性值如果是数字，会按顺序排序出来，试试用数组
            '999':'广东',
            '200':'广州',
            '755':'深圳',
            '754':'汕头',
            '757':'佛山',
            '661':'茂名'
        };
        let optionArr = [
            {
                id: '999',
                name: '广东'
            },{
                id: '200',
                name: '广州'
            },{
                id: '755',
                name: '深圳'
            },{
                id: '754',
                name: '佛山'
            },{
                id: '661',
                name: '茂名'
            }
        ];
        const {currentSelect,showOption} = this.state;
        return (
            <div className="AppBox">
                <div className="selectBox" style={selectBoxStyle}>
                    {/*选项框组件开始*/}
                    <div className="option-box" style={optionBoxStyle}
                         onClick={this.showOptionList.bind(this)}>
                        {(optionArr[currentSelect] && optionArr[currentSelect]['name']) || '请选择'}
                        {/*{optionArr[currentSelect]}*/}
                        {
                            showOption ? (<ul className="option-list" style={optionListStyle}>
                                {/*{_.map(optionObj,(item,dex)=>{*/}
                                    {/*return <li key={dex} data-key={dex}*/}
                                               {/*onClick={this.getOptionVal.bind(this)}*/}
                                               {/*className={currentSelect===dex ? 'option-item-select':''}>*/}
                                        {/*{item}*/}
                                    {/*</li>*/}
                                {/*})}*/}
                                {
                                    optionArr.map((item,dex)=>{
                                        return (
                                            <li key={dex} data-key={dex}
                                                onClick={this.getOptionVal.bind(this)}
                                                className={+currentSelect===dex ? 'option-item-select':''}>
                                                {item.name}</li>
                                        )
                                    })
                                }
                            </ul>):null
                        }
                        <div className="option-mask-layer"
                             style={showOption ? null: {display:'none'}}></div>

                    </div>
                    {/*选项框组件结束*/}
                </div>
            </div>

        );
    }
}
