<template>
    <div class="radio-demo">
      <nut-docheader 
        :name="$route.name" 
        :chName="$route.params.chnName" 
        type="Component" 
        desc="单选按钮。" 
        :showQrCode="true"></nut-docheader>
        <!-- DEMO区域 -->
        <!-- <nut-switch :height="30" :width="60" @switch-on="switchOn" @switch-off="switchOff"></nut-switch> -->
        <h5>示例</h5>
        <h6>默认用法</h6>
        <nut-radio :checked.sync="radio1"></nut-radio> 
        <div>radio1: {{radio1}}</div>
        <nut-codebox :code="demo1"></nut-codebox>        
        <!-- <pre><code v-highlight v-text="demo1"></code></pre> -->
        <h6>点击触发回调</h6>
        <nut-radio value="vv" @input-check="callback"></nut-radio>
        <nut-codebox :code="demo2"></nut-codebox>        
        <!-- <pre><code v-highlight v-text="demo2"></code></pre> -->
        <nut-codebox code="export default {
  methods:{
      callback(checkedStatus,event){
            alert(checkedStatus);
      }
  }
}"></nut-codebox>
        
        <!-- <pre><code v-highlight>export default {
  methods:{
      callback(checkedStatus,event){
            alert(checkedStatus);
      }
  }
}</code></pre> -->
        <h6>禁用选项</h6>
        <nut-radio :disabled="true"></nut-radio>
        <nut-radio></nut-radio>
        <nut-codebox :code="demo3"></nut-codebox>        
        
        <!-- <pre><code v-highlight v-text="demo3"></code></pre> -->
        <h5>Props</h5>
        <div class="tbl-wrapper">
        <table class="u-full-width">
          <thead>
            <tr>
              <th>参数</th>
              <th>说明</th>
              <th>类型</th>
              <th>默认值</th>
              <th>可选值</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>value</td>
              <td>input的value属性</td>
              <td>Number，String</td>
              <td>''</td>
              <td>--</td>
            </tr>
            <tr>
              <td>id</td>
              <td>input的id属性</td>
              <td>Number，String</td>
              <td>''</td>
              <td>--</td>
            </tr>
            <tr>
              <td>checked.sync</td>
              <td>是否选中</td>
              <td>Boolean</td>
              <td>false</td>
              <td>true/false</td>
            </tr>
            <tr>
              <td>disabled</td>
              <td>是否禁用</td>
              <td>Boolean</td>
              <td>false</td>
              <td>true/false</td>
            </tr>
          </tbody>
        </table>
        </div>

        
        <h5>Events</h5>
        <div class="tbl-wrapper">
        <table class="u-full-width">
          <thead>
            <tr>
              <th>事件名</th>
              <th>说明</th>
              <th>回调参数</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>input-check</td>
              <td>选择时触发回调函数</td>
              <td>是否选中、value、事件对象</td>
            </tr>
          </tbody>
        </table>
        </div>
    </div>
</template>

<script>
import Vue from 'vue';

export default {
    data(){
        return{
            radio1:false,
            demo1:`<nut-radio 
:checked.sync="radio1"
></nut-radio>`,
            demo2:`<nut-radio 
@input-check="callback"
></nut-radio>`,
            demo3:`<nut-radio 
:disabled="true"
></nut-radio>
<nut-radio></nut-radio>`,       
        }
    },
    components: {
    },
    methods:{
        callback(checked,value,event){
            alert(value);
            console.log(event);
        }
    }
}
</script>

<style>
.radio-demo .nut-radio{
  display: inline-block;
  margin-right:5px;
}
</style>
