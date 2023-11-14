<script lang="ts" setup>
import ImageList from '@/components/image/index.vue'
const columns = [
  {
    name: 'Name',
    dataIndex: 'name',
    key: 'name'
  },
  {
    title: 'Age',
    dataIndex: 'age',
    key: 'age'
  },
  {
    title: 'Address',
    dataIndex: 'address',
    key: 'address'
  },
  {
    title: 'Tags',
    key: 'tags',
    dataIndex: 'tags'
  },
  {
    title: 'Action',
    key: 'action'
  }
]

const data = [
  {
    key: '1',
    name: 'John Brown',
    age: 32,
    address: 'New York No. 1 Lake Park',
    tags: ['nice', 'developer']
  },
  {
    key: '2',
    name: 'Jim Green',
    age: 42,
    address: 'London No. 1 Lake Park',
    tags: ['loser']
  },
  {
    key: '3',
    name: 'Joe Black',
    age: 32,
    address: 'Sidney No. 1 Lake Park',
    tags: ['cool', 'teacher']
  }
]
</script>
<template>
  <a-space direction="vertical">
    <a-space>
      <a-button type="primary">Primary</a-button>
      <a-button type="primary" disabled>Primary(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button>Default</a-button>
      <a-button disabled>Default(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button type="dashed">Dashed</a-button>
      <a-button type="dashed" disabled>Dashed(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button type="text">Text</a-button>
      <a-button type="text" disabled>Text(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button type="link">Link</a-button>
      <a-button type="link" disabled>Link(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button danger>Danger Default</a-button>
      <a-button danger disabled>Danger Default(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button danger type="text">Danger Text</a-button>
      <a-button danger type="text" disabled>Danger Text(disabled)</a-button>
    </a-space>
    <a-space>
      <a-button danger type="link">Danger Link</a-button>
      <a-button danger type="link" disabled>Danger Link(disabled)</a-button>
    </a-space>
    <div :style="{ padding: '8px', background: 'rgb(190, 200, 200)' }">
      <a-space>
        <a-button ghost>Ghost</a-button>
        <a-button ghost disabled>Ghost(disabled)</a-button>
      </a-space>
    </div>
  </a-space>
  <a-table :columns="columns" :data-source="data">
    <template #headerCell="{ column }">
      <template v-if="column.key === 'name'">
        <span> Name </span>
      </template>
    </template>

    <template #bodyCell="{ column, record }">
      <template v-if="column.key === 'name'">
        <a>
          {{ record.name }}
        </a>
      </template>
      <template v-else-if="column.key === 'tags'">
        <span>
          <a-tag
            v-for="tag in record.tags"
            :key="tag"
            :color="tag === 'loser' ? 'volcano' : tag.length > 5 ? 'geekblue' : 'green'"
          >
            {{ tag.toUpperCase() }}
          </a-tag>
        </span>
      </template>
      <template v-else-if="column.key === 'action'">
        <span>
          <a>Invite 一 {{ record.name }}</a>
          <a-divider type="vertical" />
          <a>Delete</a>
          <a-divider type="vertical" />
          <a class="ant-dropdown-link">
            More actions
            <down-outlined />
          </a>
        </span>
      </template>
    </template>
  </a-table>
  <a-timeline>
    <a-timeline-item color="green">Create a services site 2015-09-01</a-timeline-item>
    <a-timeline-item color="green">Create a services site 2015-09-01</a-timeline-item>
    <a-timeline-item color="red">
      <p>Solve initial network problems 1</p>
      <p>Solve initial network problems 2</p>
      <p>Solve initial network problems 3 2015-09-01</p>
    </a-timeline-item>
    <a-timeline-item>
      <p>Technical testing 1</p>
      <p>Technical testing 2</p>
      <p>Technical testing 3 2015-09-01</p>
    </a-timeline-item>
    <a-timeline-item color="gray">
      <p>Technical testing 1</p>
      <p>Technical testing 2</p>
      <p>Technical testing 3 2015-09-01</p>
    </a-timeline-item>
    <a-timeline-item color="gray">
      <p>Technical testing 1</p>
      <p>Technical testing 2</p>
      <p>Technical testing 3 2015-09-01</p>
    </a-timeline-item>
    <a-timeline-item color="#00CCFF">
      <p>Custom color testing</p>
    </a-timeline-item>
  </a-timeline>
  <div class="list">
    <ImageList />
  </div>
</template>
<style scoped>
.list {
  width: 1080px;
  margin: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
