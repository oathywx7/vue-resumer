<template>
    <div id="editor">
        <div id="nav">
            <ol class="list">
                <li v-for="i in [0,1,2,3,4,5]"
                    v-bind:class="{active:currentTab === i}" 
                    v-on:click="currentTab = i">
                    <svg class="icon">
                        <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
                    </svg>
                </li>
            </ol>
        </div>

        <ol class="panes">
            <li v-bind:class="{active: currentTab === 0}">
                <profileEditor v-bind:profile="profile"/>

            </li>
            <li v-bind:class="{active: currentTab === 1}">
                <workHistoryEditor v-bind:workHistory="workHistory"/>
                  
            </li>

            <li v-bind:class="{active: currentTab === 2}">
                <EducationEditor v-bind:Education="Education"/>
                       
            </li>
            <li v-bind:class="{active: currentTab === 3}">
                <experienceEditor v-bind:experience="experience"/>
            
            </li>
            <li v-bind:class="{active: currentTab === 4}">
                <TrophyEditor v-bind:Trophy="Trophy"/>
            
            </li>
            <li v-bind:class="{active: currentTab === 5}">
                <contactEditor v-bind:contact="contact"/>
            
            </li>
        </ol>
    </div>
</template>

<script>
    import ProfileEditor from './ProfileEditor'
    import workHistoryEditor from './workHistoryEditor'
    import EducationEditor from './EducationEditor'
    import experienceEditor from './experienceEditor'
    import TrophyEditor from './TrophyEditor'
    import contactEditor from './contactEditor'

    export default {
        components:{ProfileEditor,workHistoryEditor,EducationEditor,experienceEditor,TrophyEditor,contactEditor},
        data(){
            return{
                currentTab: 0,
                icons: ['credentials_icon','work','book','aixin','jiangbei','dianhua'],
                labelPosition: '',
                profile: {
                    name: '',
                    city: '',
                    birth: '',
                },
                workHistory: [{
                    company: '',
                    dexc: '',
                    value6: '',
                }],
                Education: {
                    school: '',
                    content: '',
                },
                experience: [
                    {
                        project: '',
                        content: '',
                    }
                ],
                Trophy: [{
                    name: '',
                    content: '',
                }],
                contact: {
                    photo: '',
                    email: '',
                    palce: '',
                }
            }
        },
        
        
    }
</script>

<style>
  #editor{
      display: flex;
  }
  #nav{
      background: #000;
      width: 80px;
  }
  .list > li{
      padding: 8px 0;
      text-align: center;
  }
  .list > li.active{
      background:white;
  }
  .list > li.active >.icon{
      fill: black;
  }

  .icon{
      width: 32px;
      height: 80px;
      fill: #ddd;
      
  }
  .panes{
      flex: 1;
  }
  .panes > li{
      display: none;
      padding: 32px;
      height: 100%;
      overflow: auto;
  }
  .panes > li.active{
      display: block;
  }
  
</style>