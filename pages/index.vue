<template>
  <section>
    <header>
      <span v-html="title"></span>
      <div class="bg-blue-500 text-white p-4">
        오늘의 할일을 내일로 미루자!
      </div>
    </header>
    <main>
      <div>
        <div>
          <!-- v-for 안의 요소를 배열의 길이 만큼 반복하여 출력한다. -->
          <div v-for="item in checkList" :key="item.id">
            <input
              type="checkbox"
              :id="'check-' + item.id"
              :name="item.name"
              v-model="item.checked"
            />
            <label :for="'check-' + item.id">{{ item.name }}</label>
          </div>
        </div>
        <div>
          <button
            class="py-2 px-4 font-semibold rounded-lg shadow-md text-white bg-green-500 hover:bg-green-700"
            @click="
              checkList.push({
                id: checkList.length + 1,
                name: '할일 추가',
                checked: false
              })
            "
          >
            할일 추가
          </button>
        </div>
      </div>
    </main>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: "<h1 class='title'>TODO LIST</h1>",
      checkList: [
        { id: 1, name: '밥먹기', checked: false },
        { id: 2, name: '양치하기', checked: false },
        { id: 3, name: '숙제하기', checked: false },
        { id: 4, name: '발닦기', checked: false }
      ]
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
  .container {
    @apply min-h-screen flex justify-center items-center text-center mx-auto;
  }
  */
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
