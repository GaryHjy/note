##### ES6中的react

1.创建组件：

使用class来创建组件

class App extends React.Component {

}


2.默认状态的设置

在es6中不再使用getInitialState来设置默认状态，而是在constructor里面直接给this.state上挂载状态

class App extends Component {
	constructor(props){
		super(props)
		
		this.state={
			doing:'吃饭'
		}
	}
}

3. 默认属性的设置

在es6中，通过给类设置defaultProps属性来设置默认属性

App.defaultProps = {
	name:'App根组件'
}

4. 做属性传参验证


import PropTypes from 'prop-types';

App.propTypes = {
	name:PropTypes.string
}


5.钩子函数有变化

getDefaultProps、getInitialState没有了

多出了constructor,而这个函数本身是类的构造器，在这里相当于getDefaultProps、getInitialState的结合