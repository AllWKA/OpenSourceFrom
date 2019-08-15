<template>
  <div class="form-email-container">
    <label>{{label}}:</label>
    <input
      :placeholder="placeHolder"
      :type="type"
      :autocomplete="autocomplete"
      :disabled="disabled"
      :value="value.value"
    />
  </div>
</template>

<script>
export default {
  name: "form-email",
  props: {
    config: {}
  },
  data() {
    return {
      label: "",
      autocomplete: {
        exist: false,
        value: false
      },
      type: {
        exist: false,
        value: "text"
      },
      disabled: {
        exist: false,
        value: false
      },
      max: {
        exist: false,
        value: ""
      },
      step: {
        exist: false,
        value: ""
      },
      name: {
        exist: false,
        value: ""
      },
      value: {
        exist: false,
        value: ""
      },
      placeHolder: {
        exist: false,
        value: ""
      },
      maxlength: {
        exist: false,
        value: ""
      },
      minlength: {
        exist: false,
        value: ""
      },
      multiple: {
        exist: false,
        value: ""
      },
      pattern: {
        exist: false,
        value: ""
      },
      readonly: {
        exist: false,
        value: ""
      },
      spellcheck: {
        exist: false,
        value: ""
      }
    };
  },
  created() {
    console.log(this.config.value);
    this.initializeSttributes();
  },
  methods: {
    initializeSttributes() {
      switch (this.config.mode) {
        case "login-username":
          this.type = "text";
          this.placeHolder = "Enter Username";
          this.autocomplete = true;
          this.label = "Username";
          break;
        case "login-pwd":
          this.type = "password";
          this.placeHolder = "Enter Password";
          this.autocomplete = false;
          this.label = "Password";
          break;
        case "credit-card":
          break;
        case "mail":
          break;

        default:
          break;
      }
      this.setOtherVariables();
    },
    setOtherVariables() {
      this.setSpellcheck();
      this.setReadonly();
      this.setPattern();
      this.setMultiple();
      this.setMinlength();
      this.setMaxlength();
      this.setPlaceHolder();
      this.setName();
      this.setStep();
      if (this.type.value == "number" || this.type.value == "date") {
        this.setMax();
      }
      this.isDisable();
      this.setType();
      this.setAutocomplete();
      this.setValue();
    },
    setValue() {
      if (this.config.value) {
        this.value.value = this.config.value;
        this.value.exist = true;
        return true;
      }
      return false;
    },
    setSpellcheck() {
      if (this.config.spellcheck) {
        this.spellcheck.value = this.config.spellcheck;
        this.spellcheck.exist = true;
        return true;
      }
      return false;
    },
    setReadonly() {
      if (this.config.readonly) {
        this.readonly.value = this.config.readonly;
        this.readonly.exist = true;
        return true;
      }
      return false;
    },
    setPattern() {
      if (this.config.pattern) {
        this.pattern.value = this.config.pattern;
        this.pattern.exist = true;
        return true;
      }
      return false;
    },
    setMultiple() {
      if (this.config.multiple) {
        this.multiple.value = this.config.multiple;
        this.multiple.exist = true;
        return true;
      }
      return false;
    },
    setMinlength() {
      if (this.config.minlength) {
        this.minlength.value = this.config.minlength;
        this.minlength.exist = true;
        return true;
      }
      return false;
    },
    setMaxlength() {
      if (this.config.maxlength) {
        this.maxlength.value = this.config.maxlength;
        this.maxlength.exist = true;
        return true;
      }
      return false;
    },
    setPlaceHolder() {
      if (this.config.placeHolder) {
        this.placeHolder.value = this.config.placeHolder;
        this.placeHolder.exist = true;
        return true;
      }
      return false;
    },
    setName() {
      if (this.config.name) {
        this.name.value = this.config.name;
        this.name.exist = true;
        return true;
      }
      return false;
    },
    setStep() {
      if (this.config.step) {
        this.step.value = this.config;
        this.step.exist = true;
        return true;
      }
      return false;
    },
    setMax() {
      if (this.config.max) {
        this.max.value = this.config.max;
        this.max.exist = true;
        return true;
      }
      return false;
    },
    isDisable() {
      if (this.config.disable) {
        this.disable.value = type;
        this.disable.exist = true;
        return true;
      }
    },
    setType() {
      if (this.config.type) {
        this.type.value = type;
        this.type.exist = true;
        return true;
      }
      return false;
    },
    setAutocomplete() {
      if (this.config.autocomplete) {
        this.autocomplete.value = this.config.autocomplete;
        this.autocomplete.exist = true;
        return true;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-email-container {
  display: flex;
  flex-flow: row;
}
.form-email-container label {
  flex-basis: 25%;
}
.form-email-container input {
  flex-basis: 75%;
}
</style>
