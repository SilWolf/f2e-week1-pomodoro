<template>
  <div class="app">
    <div id="pomodoro-master-wrapper">
      <div id="pm-padding-left">
        <div class="mdc-text-field mdc-text-field--outlined mdc-text-field--with-trailing-icon">
          <i class="material-icons mdc-text-field__icon">visibility</i>
          <input class="mdc-text-field__input" id="text-field-hero-input">
          <div class="mdc-notched-outline">
            <div class="mdc-notched-outline__leading"></div>
            <div class="mdc-notched-outline__notch">
              <label for="text-field-hero-input" class="mdc-floating-label">Name</label>
            </div>
            <div class="mdc-notched-outline__trailing"></div>
          </div>
        </div>


      </div>
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
  @import '~material-components-web/material-components-web';

  html {
    width: 100%;
    height: 100%;
  }

  body {
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
