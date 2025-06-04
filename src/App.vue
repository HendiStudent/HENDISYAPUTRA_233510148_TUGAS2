<template>
  <div class="container">
    <aside class="sidebar">
      <h2 class="sidebar-title">Pertemuan 2 dan 3</h2>
      <ul class="menu">
        <li
          v-for="item in menuItems"
          :key="item"
          @click="selectItem(item)"
          :class="{ active: item === selected }"
        >
          {{ item }}
        </li>
      </ul>
    </aside>
    <main class="content">
      <component :is="getComponentName(selected)" />
    </main>
  </div>
</template>

<script>
import Home from './components/Home.vue';
import DeclarativeRendering from './components/DeclarativeRendering.vue';
import AttributeBindings from './components/AttributeBindings.vue';
import FormBindings from './components/FormBindings.vue';
import ConditionalRendering from './components/ConditionalRendering.vue';
import ListRendering from './components/ListRendering.vue';
import ComputedProperty from './components/ComputedProperty.vue';
import LifecycleTemplateRefs from './components/LifecycleTemplateRefs.vue';
import Watchers from './components/Watchers.vue';
import PageTitle from './components/PageTitle.vue';


export default {
  name: 'LessonLayout',
  components: {
    Home,
    DeclarativeRendering,
    AttributeBindings,
    FormBindings,
    ConditionalRendering,
    ListRendering,
    ComputedProperty,
    LifecycleTemplateRefs,
    Watchers,
    PageTitle
  },
  data() {
    return {
      menuItems: [
        'Home',
        'Declarative Rendering',
        'Attribute Bindings',
        'Form Bindings',
        'Conditional Rendering',
        'List Rendering',
        'Computed Property',
        'Lifecycle dan Template Refs',
        'Watchers'
      ],
      selected: 'Home'
    };
  },
  methods: {
    selectItem(item) {
      this.selected = item;
    },
    getComponentName(selectedItem) {
      const componentMap = {
        'Home': 'Home',
        'Declarative Rendering': 'DeclarativeRendering',
        'Attribute Bindings': 'AttributeBindings',
        'Form Bindings': 'FormBindings',
        'Conditional Rendering': 'ConditionalRendering',
        'List Rendering': 'ListRendering',
        'Computed Property': 'ComputedProperty',
        'Lifecycle dan Template Refs': 'LifecycleTemplateRefs',
        'Watchers': 'Watchers'
      };
      return componentMap[selectedItem] || 'Home';
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  height: 100vh;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #333;
}

.sidebar {
  width: 260px;
  background-color: #1e293b;
  padding: 24px;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
  color: white;
  overflow-y: auto;
}

.sidebar-title {
  font-size: 22px;
  margin-bottom: 20px;
  font-weight: bold;
  color: #fbbf24;
}

.menu {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu li {
  padding: 12px;
  margin-bottom: 6px;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  word-wrap: break-word;
}

.menu li:hover {
  background-color: #334155;
}

.menu li.active {
  background-color: #fbbf24;
  color: #1e293b;
  font-weight: bold;
}

.content {
  flex: 1;
  padding: 40px;
  background-color: #f8fafc;
  overflow-y: auto;
}

.content h3 {
  font-size: 28px;
  margin-bottom: 16px;
  color: #1e293b;
}

/* Responsive design */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    height: auto;
  }
  
  .sidebar {
    width: 100%;
    height: auto;
    order: 2;
  }
  
  .content {
    order: 1;
    padding: 20px;
  }
  
  .menu {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  
  .menu li {
    flex: 1;
    min-width: 120px;
    text-align: center;
    margin-bottom: 0;
  }
}
</style>