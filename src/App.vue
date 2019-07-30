<template>
  <v-app>
    <div id="pomodoro-master-wrapper">
      <div id="pm-padding-left"></div>
      <div id="pm-left">
        <v-text-field id="pml-text-field"
          append-icon="add"
          solo flat
          placeholder="ADD A NEW MISSION..."
        ></v-text-field>

        <div>
          Current Work
        </div>

        <v-list id="pml-missions"
        >
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>The second item to do</v-list-item-title>
            </v-list-item-content>
            <v-list-item-action>
              <v-icon>play_circle_outline</v-icon>
            </v-list-item-action>
          </v-list-item>
          <v-divider></v-divider>
          
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>The third item to do</v-list-item-title>
            </v-list-item-content>
            <v-list-item-action>
              <v-icon>play_circle_outline</v-icon>
            </v-list-item-action>
          </v-list-item>
          <v-divider></v-divider>
          
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>The fourth item to do</v-list-item-title>
            </v-list-item-content>
            <v-list-item-action>
              <v-icon>play_circle_outline</v-icon>
            </v-list-item-action>
          </v-list-item>
          <v-divider></v-divider>
        </v-list>
      </div>
      <div id="pm-master-clock-wrapper">
        <div id="pm-master-clock">
          <div id="pm-master-clock-inner">
            <v-btn icon="true" class="pmmc-control-btn">
              <v-icon>play_circle_filled</v-icon>
            </v-btn>
          </div>
        </div>
      </div>
      <div id="pm-right"></div>
      <div id="pm-padding-right"></div>
    </div>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',
  data: () => ({
    //
  }),
});
</script>

<style lang="scss">
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

    > * {
      padding: 25px 12.5px;
    }

    #pm-padding-left {
      flex: 1 0 auto;
      background: var(--background-left);
    }

    #pm-left {
      flex: 0 0 505px;
      background: var(--background-left);

      display: flex;
      flex-direction: column;
      justify-content: space-between;

      > * {
        flex: 0 0 auto;
      }
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

          .pmmc-control-btn {
            width: 96px;
            height: 96px;

            .v-icon {
              color: #FFF;
              font-size: 96px;
              width: 96px;
              height: 96px;
            }
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
