<template>
  <div id="app">
    <div style="margin:10% 25%; width:250px;" >
    <br>
    <ejs-combobox :dataSource='dataItem' :fields='dataFields'
    placeholder='Select a name' popupWidth="250px" 
    popupHeight="200px" sortOrder="Descending" >
    </ejs-combobox>
    </div>
  </div>
</template>


<script>
import Vue from "vue";
import { ComboBoxPlugin} from '@syncfusion/ej2-vue-dropdowns';
Vue.use(ComboBoxPlugin);
import { DataManager, WebApiAdaptor } from "@syncfusion/ej2-data";
export default Vue.extend({
  data: function() {
    return {
      dataItem: new DataManager({
        url: 'https://ej2services.syncfusion.com/production/web-services/api/Employees',
        adaptor: new WebApiAdaptor,
        crossDomain: true
      }),
      dataFields: {value: 'EmployeeID', text: 'FirstName'}
    };
  }
});
</script>




<style>
@import url(https://cdn.syncfusion.com/ej2/material.css);
</style>
