<template>
  <div class="team-group">
    <div class="team-group-title">{{ group.name }}</div>
    <div class="team-entries">
      <TeamEntry
        v-for="(member, index) in group.members"
        :key="index"
        :member="member"
        :team="team"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import TeamEntry from '~/components/TeamMemberEntry.vue'
import TeamGroupData from '~/src/typings/TeamGroupData'
import TeamData from '~/src/typings/TeamData'

@Component({
  components: { TeamEntry },
})
export default class TeamGroupEntry extends Vue {
  @Prop({ required: true })
  group!: TeamGroupData

  @Prop({ required: true })
  team!: TeamData
}
</script>

<style scoped>
.team-group {
  position: relative;
  width: 100%;
  background-color: white;
  box-shadow: 0 0 12px -4px #000;
  border-radius: 20px;
  margin: 100px 0;
  display: flex;
  color: black;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.team-group .team-group-title {
  margin-top: 20px;
  font-size: 2vw;
  height: 30px;
}

.team-group .team-entries {
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 40px;
}
</style>
