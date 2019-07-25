<template>
    <el-tree
            :data="data"
            :default-checked-keys="[5]"
            :default-expanded-keys="[2, 3]"
            :props="defaultProps"
            node-key="id"
            show-checkbox
    ></el-tree>
</template>

<script>
  export default {
    name: 'tree',
    data() {
      return {
        data: [{
          id: 1,
          label: '一级 1',
          children: [{
            id: 4,
            label: '二级 1-1',
            wrapperClass: 'nihao',
            children: [{
              id: 9,
              label: '三级 1-1-1'
            }, {
              id: 10,
              label: '三级 1-1-2'
            }]
          }]
        }, {
          id: 2,
          label: '一级 2',
          children: [{
            id: 5,
            label: '二级 2-1'
          }, {
            id: 6,
            label: '二级 2-2'
          }]
        }, {
          id: 3,
          label: '一级 3',
          children: [{
            id: 7,
            label: '二级 3-1'
          }, {
            id: 8,
            label: '二级 3-2'
          }]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    }
  }
  ;
</script>
<style>
    .el-tree-node.is-expanded > .el-tree-node__children.nihao {
        display: flex;
    }
</style>
