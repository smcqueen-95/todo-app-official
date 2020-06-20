<template>
 <div>
    <div>
  <b-navbar variant="dark" type="dark" class="navbar">
    <b-navbar-brand>Tasks To Do</b-navbar-brand>
    
    <b-button v-b-toggle.sidebar-1 class="btn btn-outline-info">Menu</b-button>
  <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit" variant="outline-success" >Search</b-button>
        </b-nav-form>


        <b-nav-item-dropdown right >
          <!-- Using 'button-content' slot -->
          <template v-slot:button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
  </b-navbar>
</div>

    <b-sidebar id="sidebar-1" title="ToDo App Menu" bg-variant="dark" text-variant="light" shadow >
     
          <nav class="mb-3">
            <b-nav vertical>
 
              <p> <b-avatar class="avatar" variant="primary"></b-avatar> 
               <br/>
               <br/>
               This is a sidebar that shows the different navigations through the ToDo App</p>
             <br/>
              <b-nav-item href="#link-1" @click="hide">Projects</b-nav-item>
              <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>
            </b-nav>
          </nav>
        
    </b-sidebar>
  </div>
     
</template>

<script>

export default {
    name: "Sidebar"
}
</script>

<style scoped>
.btn{
    margin-left: 50px;
}
.navbar{
  margin-top: 10px;
  margin-left: 50px;
  margin-right: 50px;
}
.btn{
  margin-left: 10px;
}
.text{
  position: right;
  margin-left: 150px;
}
.my-2{
  margin-right: 20px;
  position: right;
}
p{
  text-align: center;
  margin-left: 20px;
  margin-right:20px;
}
.avatar{
  position: left;
  margin-left: 10px;
}
</style>