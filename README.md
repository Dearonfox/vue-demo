## 변경요약

상태: data() → ref / reactive

계산값: computed: → computed()

메서드: methods → setup 내부 함수

감시자: watch: → watch()

생명주기: mounted() 등 → onMounted() 등 Composition 훅

템플릿: 기존 바인딩({{ }}, v-model, 각종 디렉티브) 유지. JS 코드에서만 ref는 .value로 접근

ESLint/버전 이슈: 프로젝트가 Vue 3.2라 <script setup> 매크로 중 defineOptions는 미사용.
컴포넌트 이름·props는 보조 <script>의 export default { name, props } 또는 defineComponent({ props })로 선언
E12ReFComponent 동작 예시
![E12RefComponent Focus Demo](./src/assets/실행결과.png)