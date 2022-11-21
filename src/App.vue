<template>
  <div class="flex-container">
    <div class="flex-child">
      <div class="submenu-container">
        <vue-collapsible-panel-group class="custom-vcp">
          <vue-collapsible-panel :expanded="true">
            <template #title>
              <div class="submenu-entry">Names</div>
            </template>
            <template #content>
              <div v-if="nameList === undefined || nameList.length === 0">
                <div></div>
              </div>
              <div
                v-for="name in nameList"
                :key="name.id"
                class="items-clickable"
              >
                <div
                  :class="`submenu-entry-items ${
                    name.id === selectedName?.id ? 'selected' : ''
                  }`"
                >
                  {{ name.name }}
                </div>
              </div>
            </template>
          </vue-collapsible-panel>

          <vue-collapsible-panel :expanded="true">
            <template #title>
              <div class="submenu-entry">Another Names</div>
            </template>
            <template #content>
              <div
                v-if="
                  anotherNameList === undefined || anotherNameList.length === 0
                "
              >
                <div></div>
              </div>
              <div
                v-for="name in anotherNameList"
                :key="name.id"
                class="items-clickable"
              >
                <div
                  :class="`submenu-entry-items ${
                    name.id === selectedName?.id ? 'selected' : ''
                  }`"
                >
                  {{ name.name }}
                </div>
              </div>
            </template>
          </vue-collapsible-panel>

        </vue-collapsible-panel-group>
      </div>
    </div>
  </div>
</template>

<script>
import {
  VueCollapsiblePanel,
  VueCollapsiblePanelGroup,
} from "@dafcoe/vue-collapsible-panel";

export default {
  components: {
    VueCollapsiblePanel,
    VueCollapsiblePanelGroup,
  },
  data() {
    return {
      nameList: [
        {
          id: 1,
          name: "Jhon",
        },
        {
          id: 2,
          name: "Paul",
        },
        {
          id: 3,
          name: "Mary",
        },
      ],
      anotherNameList: [
        {
          id: 4,
          name: "Peter",
        },
        {
          id: 5,
          name: "Michael",
        },
      ],
      selectedName: {
        id: 2,
        name: "Paul",
      },
    };
  },
};
</script>

<style lang="scss">
.custom-vcp {
  section.vcp--expanded {
    header {
      div > .submenu-entry {
        font-weight: 700;
        font-size: 14px;
        line-height: 150%;
        color: #33383f;
      }

      .vcp__header-icon > span > svg {
        transform-origin: center;
        transform: rotate(180deg);
      }
    }
  }

  section {
    color: #788190;
    cursor: pointer;

    header {
      display: flex;
      width: 100%;
      align-content: center;
      align-items: center;
      flex-direction: row;
      justify-content: space-around;

      div.vcp__header-title {
        width: 80%;
      }

      div.vcp__header-icon {
        width: 20%;
      }
    }
  }
}
</style>

<style lang="scss" scoped>
.flex-container {
  margin-top: -76px;
  display: flex;
  height: 100%;
}

.flex-child {
  background-color: #fcfcfc;
  width: 88px;

  img.back-arrow {
    margin-left: 30px;
    margin-top: 22px;
  }
}

.flex-child:last-child {
  background-color: #f6f7f8;
  width: 200px;
  img {
    margin-left: 35px;
    margin-top: 16px;
  }
}

.menu-entries {
  padding: 5px;
  div {
    margin-top: 70px;
    padding: 5px;
    text-align: center;
    color: #003478;
    font-size: 12px;
    background: #d9e1eb;
    border-radius: 8px;
    img {
      margin-top: 15px;
    }
  }
}

.submenu-container {
  margin-top: 35px;
}

.submenu-entry {
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 150%;

  margin-top: 5px;
  color: #788190;
  width: 190px;
  text-align: left;
  border-bottom: 1px solid #e1e4e8;
  padding: 10px;
  cursor: pointer;
  img.menu-entry {
    float: right;
    margin-top: 7px;
  }
}

.submenu-entry-items {
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 150%;
  color: #33383f;
  margin-top: 8px;

  &.selected {
    background: #d9e1eb;
    border-radius: 8px;
    padding: 0px 10px;
    font-weight: 700;
    font-size: 14px;
    line-height: 150%;
    color: #003478;
  }
}

.items-clickable {
  display: inline-block;
  width: 100%;
}
</style>
