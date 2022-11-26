<template >
	<div>
		<Menu />	
		<!-- BEGIN MICROPOSTS -->

    <div class="row">
    <div class="col-md-6" v-for="micropost in microposts" :key="micropost.id">
      <div class="blogPost">
        <div class="card">
          <img src="images/IamMarinush.png" class="card-img-top" alt="ruka">
          <div class="card-body">
            <h4 class="card-title"><strong>{{micropost.title}}</strong></h4>

            <div :id="`multiCollapseExample1{{micropost.id}}`" :class="`multi-collapse{{micropost.id}} collapse show `" style="">
              <p class="card-text text-truncate">

                {{micropost.content}}
              </p>
            </div>
            <p>
              <button class="btn btn-primary" type="button" data-toggle="button" data-bs-toggle="collapse" :data-bs-target="`.multi-collapse{$micropost.id}`" aria-expanded="false" :aria-controls="`multiCollapseExample1{{micropost.id}} multiCollapseExample2{{micropost.id}}`" autocomplete="off">
                Expand
              </button>
            </p>

            <div :id="`multiCollapseExample2{{micropost.id}}`" :class="`multi-collapse{{micropost.id}} collapse`" style="">
              <div class="card-body">
                <p class="card-text">
                  {{micropost.content}}
                </p>
              </div>
            </div>

            <div class="row" style="padding-left:30px;">
              <div class="col-12">
                <p>by {$NAMES[$micropost.user_id]}</p>
              </div>
              <div class="col">

                <p>
                  Created: {$micropost.created_at|date_format:"%d-%m-%Y"}
                </p>
              </div>
              <div class="col">

                <p>
                  Updated: {$micropost.updated_at|date_format:"%d-%m-%Y"}
                </p>
              </div>
              <div class="col">
                {if $USER.id eq $micropost.user_id}
                <a href="#" class="card-link">update</a>
                {/if}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    </div>
		<!-- END MICROPOSTS -->

		<Footer />

	</div>
</template>

<script>
import Footer from '@/components/Footer.vue'
import Menu from '@/components/Menu.vue'

export default {
	components: {
		Footer,
        Menu
	},
	data() {
		return {
			microposts: [],
			comments: [],
			user: {
				id: '', 
				name: '', 
				email: '', 
				session_id: ''
			},
			show: '',
		}
	},
	mounted() {
    this.getMicropost();
	},
	methods: {
    async getMicropost(){
      try{
        this.microposts = this.$store.dispatch('microposts/getMicroposts')
      }
      catch(error){
        console.log(error);
      }
    }
	},
	computed: {

	}
}
</script>

<style scoped>

</style>