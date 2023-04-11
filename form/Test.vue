<template>
  <div style="margin: 30px">
    <Form :data="formData"></Form>
  </div>
</template>

<script>
import Form from "./Form.vue";

export default {
  name: "Test",
  components: { Form },
  data() {
    return {
      formData: {
        width: "100px",
        items: [
          {
            type: "Input",
            label: "合约名称:",
            prop: "contractName",
            width: "240px",
            placeholder: "请输入您的合约名称",
            default: "",
          },
          {
            type: "Input",
            label: "数据源URL:",
            prop: "dataSourceURL",
            width: "240px",
            placeholder: "请输入您的数据源URL",
            default: "",
          },
          {
            type: "Input",
            label: "数据路径:",
            prop: "dataPath",
            width: "240px",
            placeholder: "请输入您的数据路径",
            default: "",
          },
          {
            type: "Input",
            label: "预言机合约地址:",
            prop: "contractAddress",
            width: "240px",
            placeholder: "请输入您选择的预言机合约地址",
            default: "",
          },
          {
            type: "Input",
            label: "JobId:",
            prop: "JobIdName",
            width: "240px",
            placeholder: "请输入对应的的JobId",
            default: "",
          },
        ],
        buttons: [
          {
            label: "确定",
            type: "primary",
            action: "submit",
            call: (data) => {
              console.log(data);
            },
          },
          {
            label: "重置",
            type: "primary",
            action: "reset",
            call: () => {
              console.log("reset");
            },
          },
          {
            label: "其他",
            type: "primary",
            call: (data) => {
              console.log(data);
            },
          },
        ],
        rules: {
          contractName: [
            { required: true, message: "请输入您的合约名称", trigger: "blur" },
            {
              min: 3,
              max: 5,
              message: "长度在 3 到 5 个字符",
              trigger: "blur",
            },
          ],
          dataSourceURL: [
            { required: true, message: "请输入您的数据源URL", trigger: "blur" },
            {
              min: 3,
              max: 5,
              message: "长度在 3 到 5 个字符",
              trigger: "blur",
            },
          ],
          dataPath: [
            { required: true, message: "请输入您的数据路径", trigger: "blur" },
            {
              min: 3,
              max: 5,
              message: "长度在 3 到 5 个字符",
              trigger: "blur",
            },
          ],
          contractAddress: [
            {
              required: true,
              message: "请输入您选择的预言机合约地址",
              trigger: "blur",
            },
            {
              min: 3,
              max: 5,
              message: "长度在 3 到 5 个字符",
              trigger: "blur",
            },
          ],
          JobIdName: [
            { required: true, message: "请输入对应的的JobId", trigger: "blur" },
            {
              min: 3,
              max: 5,
              message: "长度在 3 到 5 个字符",
              trigger: "blur",
            },
          ],
        },
      },
    };
  },
};
</script>

<style scoped></style>
