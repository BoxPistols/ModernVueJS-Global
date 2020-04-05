<template>
  <div>
    <Member
      :changeHeight="changeHeight"
      :key="member.id"
      v-for="member in members"
      :member="member"
    >{{member.name}}</Member>
  </div>
</template>

<script>
import Member from "./components/Member";
export default {
  name: "App",
  components: {
    Member
  },
  data() {
    return {
      members: [
        { name: "中西", position: "ガード", id: 1, height: 163 },
        { name: "佐々木", position: "フォワード", id: 2, height: 173 },
        { name: "渡辺", position: "センター", id: 3, height: 180 },
        { name: "城所", position: "パワーフォワード", id: 4, height: 176 },
        { name: "荒瀬", position: "シューティングガード", id: 5, height: 168 }
      ]
    };
  },
  methods: {
    changeHeight(id, value) {
      const members = this.members;
      this.members = members.map(member => {
        if (id === member.id) {
          return { ...member, height: member.height + value };
        }
        return member;
      });
    }
  }
};
</script>

<style>
</style>
