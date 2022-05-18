<template>
  <Menu @changePlace="place = $event"/>
  <div class="container">
    <Start :place="place"/>
    <Benefits />
    <How />
    <Room />
    <Button />
  </div>
</template>

<script>
import Menu from './components/Menu.vue';
import Button from './components/Button.vue';
import Benefits from './components/Benefits.vue';
import How from './components/How.vue';
import Room from './components/Room.vue';
import Start from './components/Start.vue';

export default {
  components: {
    Menu,
    Start,
    Button,
    Benefits,
    How,
    Room
  },
  data() {
    return {
      place: 'квартир'
    }
  },
  methods: {

  }
}
</script>

<style lang="scss">

.container {
  position: relative;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;

}
</style>
