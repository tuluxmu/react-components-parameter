#react-Parameter

##Demo

<a href="http://tuluxmu.github.io/react-components-parameter/">Click here</a>

##Install

```
git clone https://github.com/tuluxmu/react-components-parameter.git
cd react-components-parameter
npm Install //download the dependencies file
webpack //pack the file
```
##Usage

```
import React from 'react';
import {render} from 'react-dom';
import { createStore,bindActionCreators } from 'redux';
import { Provider ,connect} from 'react-redux';
import Parameter from './components/Parameter/Parameter.jsx';
const requestParameters = {
  appid:{
    value:'1',
    comment:0
  }
}
export class Index extends React.Component {
    constructor(props) {
      super(props);
    }
    onEditParameter(name, value) {
      console.log('changeValue', name, value);
    }
    onInsertParameter(name, value) {
      console.log('insert', name, value);
    }
    render() {
      const onEditParameter = this.onEditParameter.bind(this);
      const onInsertParameter = this.onInsertParameter.bind(this);
      return(
        <Parameter parameters={requestParameters}
            onEditItem={onEditParameter}
            onInsertParameter={onInsertParameter}
          />
      );
    }
}
render(<Index/>,document.getElementById('root'));
```

##Properties

Name | Description | Type | Required | Default value
-----|-------------|------|----------|--------------
parameters | parameters | json | yes |  { appid:{ value:'1',comment:0} }
onEditItem | onEditItem | func | yes |  onEditParameter(name, value) 
onInsertParameter | onInsertParameter | func | yes | onInsertParameter(name, value)
