<template>
    <div class="panel-body">
        <div class="table-responsive">
            <table :class="tableClass">
                <colgroup>
                    <col v-for="(item,i) in tableprop" :key="i" :width="item.width" :align="item.align" />
                </colgroup>
                <thead>
                    <tr>
                        <th v-for="(item,i) in tableprop" :key="i">{{item.label}}</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(item,i) in tabledata" :key="i">
                        <td v-for="(propItem,propIndex) in tableprop" :key="propIndex">{{item[propItem.prop]}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
    module.exports = {
      name: 'dataTable',
      props: {
	    tableClass:{
		    type: String,
		    default:'table no-margin'
	    },
	    tabledata: Array,
	    tableprop: Array
      }
    }
</script>