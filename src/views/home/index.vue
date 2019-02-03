<template>
  <el-row>
    <el-table ref="table" :data="tableData" border style="width: 100%">
      <el-table-column prop="sequence" width="200" label="题目序号" align="center">
        <template slot-scope="scope">
          <el-input-number v-if="editRow === scope.row" v-model="sequence" :min="1" label="题目序号"></el-input-number>
          <span v-else>{{scope.row.sequence}}</span>
        </template>
      </el-table-column>
      <el-table-column prop="id" width="100" label="题目编号" align="center">
      </el-table-column>
      <el-table-column prop="name" width="200" label="题目名称" align="center">
      </el-table-column>
      <el-table-column prop="exerciseInfo" label="题目信息" align="center">
      </el-table-column>
      <el-table-column label="操作" align="center">
        <template slot-scope="scope">
          <el-button type="primary" size="small" plain @click="editSubject(scope.row)">编辑</el-button>
          <el-button @click="deleteSubject(scope.$index, scope.row)" type="danger" plain size="small">删除</el-button>
        </template>
      </el-table-column>
    </el-table>
  </el-row>
</template>
<script>
//////    http://47.112.6.219/tsapi/admuser/loginByPas      -----------登录 post
/* 
  {
    check: 'stropsutgnet',
    phone: '17600185137',
    pass: 'abcdeabcdeabcdeabcdeabcdeabcdeabcdeabcdeabcde'
  }
*/
//////    http://47.112.6.219/tsapi/admapi/groupUser      -----------分组用户 post
/* 
  {
    check: 'stropsutgnet',
    token: '17600185137',
    skip: 0,
    limit: 20,
    keyword: beijing
  }
*/
//////    http://47.112.6.219/tsapi/admapi/groups      -----------所有分组 post
/* 
  {
    check: 'stropsutgnet',
    token: '17600185137'
  }
*/
//////    http://47.112.6.219/tsapi/admapi/allUser      -----------所有用户 post
/* 
  {
    check: 'stropsutgnet',
    phone: '17600185137',
    skip: 0,
    limit: 20,
  }
*/

export default {
  data() {
    return {
      tableData: []
    };
  },
  methods: {
    editSubject() {},
    deleteSubject() {}
  }
};
</script>
<style lang="scss" scoped>
.el-row {
  padding: 20px;
}
</style>
