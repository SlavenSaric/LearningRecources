<template>
  <base-dialog v-if="inputIsInvalid" title="Invalid Input" @close="confirmError">
  <template #default>
    <p>Infortunately, at leat one input is invalid</p>
    <p>Please check your input and make sure you enter a few characters into each field</p>
  </template>
  <template #actions>
    <base-button @click="confirmError">Okay</base-button>
  </template>
</base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput"/>
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="3" ref="descInput"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div>
        <base-button type="submit">Add Recource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
    export default {
        inject: ['addRecource'],
        data(){
          return {
            inputIsInvalid: false
          }
        },
        methods: {
            submitData(){
                const enteredTitle = this.$refs.titleInput.value
                const enteredDesc = this.$refs.descInput.value
                const enteredLink = this.$refs.linkInput.value

                if(enteredTitle.trim() === '' || enteredDesc.trim() === '' || enteredLink.trim() === ''){
                  this.inputIsInvalid = true
                  return
                }

                this.addRecource(enteredTitle, enteredDesc, enteredLink)
                this.$refs.titleInput.value = ''
                this.$refs.descInput.value = ''
                this.$refs.linkInput.value = ''
            },
            confirmError(){
              this.inputIsInvalid = false
            }
        }
    }
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>