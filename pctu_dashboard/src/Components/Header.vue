<template>
  <header>
<div class="container">

<div>
  <b-navbar toggleable="lg" type="dark" variant="info">
  

    <b-collapse id="nav-collapse" is-nav>
     

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>

        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template v-slot:button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>

    <div class="row">
        <div class="col-md-2">
              <label class="typo__label">Vùng</label>
                <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
                    <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                    v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
                </multiselect>
        </div>
        <div class="col-md-2">
             <label class="typo__label">Tỉnh thành</label>
            <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
                <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
        </div>
          <div class="col-md-2">
             <label class="typo__label">Chi nhánh</label>
            <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
                <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
        </div>

          <div class="col-md-2">
             <label class="typo__label">Doi tac</label>
            <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
                <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
        </div>

           <div class="col-md-2">
                <label class="typo__label">Nhân viên</label>
                <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
                    <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                    v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
                </multiselect>
            </div>

            
    </div>


 
</div>
 

<!-- <table> 
 <tr>
     <th w> 
        <label class="typo__label">Vùng</label>
    <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
        <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
        v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
    </multiselect>
    </th> 

     <th> 
         <label class="typo__label">Tỉnh thành</label>
        <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
            <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
    </th> 

     <th> 
         <label class="typo__label">Doi tac</label>
        <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
            <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
    </th> 

     <th> 
         <label class="typo__label">Doi tac</label>
        <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
            <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
    </th> 

     <th> 
         <label class="typo__label">Doi tac</label>
        <multiselect v-model="value" :options="options" :multiple="true" :close-on-select="false" :clear-on-select="false" :preserve-search="true" placeholder="Pick some" label="name" track-by="name" :preselect-first="true">
            <template slot="selection" slot-scope="{ values, search, isOpen }"><span class="multiselect__single" 
                v-if="values.length>1 /*&amp;&amp;*/ & !isOpen">{{ values.length }} selected</span></template>
            </multiselect>
    </th> 
</tr>

</table>  -->


   </header>
</template>

<script>
import Multiselect from 'vue-multiselect'

export default {
    name:'headers',
    components: {
    Multiselect
  },
  data () {
    return {
      value: [],
      options: [
        { name: 'Vue.js', language: 'JavaScript' },
        { name: 'Adonis', language: 'JavaScript' },
        { name: 'Rails', language: 'Ruby' },
        { name: 'Sinatra', language: 'Ruby' },
        { name: 'Laravel', language: 'PHP' },
        { name: 'Phoenix', language: 'Elixir' }
      ]
    }
  }

}
</script>

<style >
.head{
    display: inline-block;
    margin: auto;
}
.container{
    display: inline;
}

</style>