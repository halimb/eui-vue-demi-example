<script lang="ts">
import { defineComponent } from 'vue'
import { ETimeline } from '@evercam/ui/vue3'

export default defineComponent({
  name: 'TimelineWrapper',
  components: {
    ETimeline
  },
  setup() {
    const eventsGroups = {
      Group1: {
        label: "Group 1",
        color: "#eee",
        events: [
          {
            startDate: new Date("2022-12-10T00:00:00").getTime(),
            endDate: new Date("2022-12-15T01:00:00").getTime(),
            color: "#5f6b43",
            text: "Holiday"
          },
          {
            startDate: new Date("2023-01-01T00:00:00").getTime(),
            endDate: new Date("2023-03-01T00:00:00").getTime(),
            color: "#5f6b43",
            text: "Q1 2023"
          }
        ]
      },
      Group2: {
        label: "Group 2",
        color: "#eee",
        events: [
          {
            startDate: new Date("2023-02-01T00:00:00").getTime(),
            endDate: new Date("2023-04-01T00:00:00").getTime(),
            color: "#5f6b43",
            text: "Q1-Q2 2023"
          }
        ]
      }
    }

    return {
      eventsGroups
    }
  }
})
</script>

<template>
  <div class="timeline-container" style="width: 500px;">
    <ETimeline
      :events-groups="eventsGroups"
      :bar-height="35"
      :bar-y-padding="5"
      min-date="2021-01-15"
      max-date="2025-10-15"
      tooltip-top
      :dark="false"
      @hovered-timestamp="() => {}"
      @visible-interval-change="() => {}"
    />
  </div>
</template>

<style scoped>
.timeline-container {
  clip-path: inset(-100px 0px 0px 0px);
}
</style>
