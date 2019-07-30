<template>
  <div class="app">
    <div id="pomodoro-master-wrapper">
      <div id="pm-padding-left"></div>
      <div id="pm-left"></div>
      <div id="pm-master-clock-wrapper">
        <div id="pm-master-clock">
          <div id="pm-master-clock-inner">
            <button class="mdc-icon-button material-icons pmmc-control-button">play_circle_filled</button>
          </div>
        </div>
      </div>
      <div id="pm-right"></div>
      <div id="pm-padding-right"></div>
    </div>
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'

  export default {
    data () {
      return {
        
      }
    },
    components: { HelloWorld }
  }
</script>

<style lang="scss">
  // First, set the value for variable
  $mdc-typography-font-family: "Roboto Mono", monospace;

  // Then, import required files
  @import "@material/typography/mixins";
  @import "@material/button/mdc-button";
  @import "@material/icon-button/mdc-icon-button";

  html {
    width: 100%;
    height: 100%;
  }

  body {
    @include mdc-typography(body2);

    width: 100%;
    min-height: 100%;
    margin: 0;
  }

  #pomodoro-master-wrapper {
    display: flex;
    align-items: stretch;
    width: 100%;
    height: 100vh;
    margin-left: auto;
    margin-right: auto;

    --background-left: #FFEDF7;
    --background-right: #003164;
    --clock-background-color: #FF4384;

    #pm-padding-left {
      flex: 0 1 auto;
      background: var(--background-left);
    }

    #pm-left {
      flex: 3 0 auto;
      background: var(--background-left);
    }

    #pm-master-clock-wrapper {
      flex: 0 0 auto;
      display: flex;
      align-items: center;
      background-image: linear-gradient(to right, var(--background-left) 50%, var(--background-right) 50%,  var(--background-right) 100%);
  
      #pm-master-clock {
        width: 510px;
        height: 510px;
        border: 3px solid var(--clock-background-color);
        padding: 12px;
        border-radius: 50%;

        #pm-master-clock-inner {
          width: 100%;
          height: 100%;
          border-radius: 50%;
          background: var(--clock-background-color);

          display: flex;
          align-items: center;
          justify-content: center;

          .pmmc-control-button {
            color: #FFF;
            font-size: 96px;
            width: auto;
            height: auto;
          }
        }
      }
    }

    #pm-master-clock-right {
      flex: 0 0 270px;
      background: var(--background-right);
      position: relative;
    }

    #pm-right {
      flex: 1 0 auto;
      background: var(--background-right);
    }

    #pm-padding-right {
      flex: 0 1 auto;
      background: var(--background-right);
    }
  }
</style>
