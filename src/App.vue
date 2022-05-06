<template>
  <h1>{{ count }}</h1>
</template>

<script>
export default {
  data() {
    return {
      count: 2
    }
  },
  beforeCreate() {  // 활용도가 적음
    console.log('Before Create!', this.count); // undefined, 데이터가 정의되기 전에 실행 되므로 undefined가 나온다.
  },
  created() { // 활용도가 높음
    console.log('Created!', this.count);  // 2, 생성 직후라 데이터가 출력이 된다.
    console.log(document.querySelector('h1'));  // null, html과 연결이 되기 전이기 때문에 검색을 할 수 없다.
  },
  beforeMount() { // 활용도가 적음
    console.log('Before Mounte!');
    console.log(document.querySelector('h1'));  // null, html과 연결이 되기 전이기 때문에 검색을 할 수 없다.
  },
  mounted() { // 활용도가 높음
    console.log('Mounted!');
    console.log(document.querySelector('h1'));  // <h1>2</h1>, 화면에 렌더링 된 후를 조회하려면 mounted에서 확인해야 한다.
  }
}
</script>