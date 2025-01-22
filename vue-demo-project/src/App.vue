<script setup>
  // import component มาจาก folder components
  import MyHello from './components/MyHello.vue';
  import Variable from './components/Variable.vue';
  import Counter from './components/Counter.vue';
  import Calculator from './components/Calculator.vue';
  import MultiplicationTable from './components/MultiplicationTable.vue';
  import MyButton from './components/MyButton.vue';
  import ParentAndChild from './components/ParentAndChild.vue';
  import FormInputValidation from './components/FormInputValidation.vue';
  import DropdownListAndArray from './components/DropdownListAndArray.vue';
  import CheckBoxAndRadio from './components/CheckBoxAndRadio.vue';
  import DisabledButton from './components/DisabledButton.vue';
  import FocusTextbox from './components/FocusTextbox.vue';
  import OnMout from './components/OnMout.vue';
  import TodoList from './components/TodoList.vue';
  import VifExample from './components/VifExample.vue';
  import VifElseExample from './components/VifElseExample.vue';
  import SearchArray from './components/SearchArray.vue';
  import UsingWatch from './components/UsingWatch.vue';
  import ComputedExample from './components/ComputedExample.vue';
  import WatchExmaple from './components/WatchExmaple.vue';
  import HttpGetExample from './components/HttpGetExample.vue';
  import HttpPostExample from './components/HttpPostExample.vue';
  import HttpPutExample from './components/HttpPutExample.vue';
  import HttpDeleteExample from './components/HttpDeleteExample.vue';

  const handleEventFromChild = (message) => {
    console.log(message)
  }

</script>

<template>
    <!-- ใช้งาน componenets -->
    <MyHello />
    <br>

    <Variable />
    <br>

    <Counter />
    <br>

    <Calculator />
    <br>

    <MultiplicationTable />
    <br>

    <MyButton text="Click me" />
    <br><hr>

    <ParentAndChild @myEvent="handleEventFromChild">
      <template #myHeader>
        <h1>Custom Header</h1>
      </template>
    </ParentAndChild>
    <br><hr>

    <FormInputValidation/>
    <br><hr>

    <DropdownListAndArray />
    <br><hr>

    <CheckBoxAndRadio />
    <br><hr>

    <DisabledButton />
    <br><hr>

    <FocusTextbox />
    <br><hr>

    <OnMout />
    <br><hr>

    <TodoList />
    <br><hr>

    <VifExample />
    <br><hr>

    <VifElseExample />
    <br><hr>

    <SearchArray />
    <br><hr>

    <UsingWatch />
    <br><hr>

    <ComputedExample />
    <br><hr>

    <WatchExmaple />
    <br><hr>

    <HttpGetExample />
    <br><hr>

    <HttpPostExample />
    <br><hr>

    <HttpPutExample />
    <br><hr>

    <HttpDeleteExample />
    <br><hr>
</template>