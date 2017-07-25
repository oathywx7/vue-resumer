<template>
    <div id="preview">
    <h1>{{resume.Profile.name || ' 请填写姓名'}}</h1>
    <hr>
    <p class="city">{{resume.Profile.city || '请填写城市'}} | {{resume.Profile.birth || '请填写出生年月'}}</p>
    <section v-if="filter(resume.workHistory).length > 0">
        <h2>工作经历</h2>
        <ul>
            <li v-for="workHistory in filter(resume.workHistory)">
                <h3>{{workHistory.company}} | {{workHistory.time}}</h3>
                 {{workHistory.dexc}}
            </li>
        </ul>
    </section>
    <div class="education">
        <h2>学习经历</h2>
        <h3>{{resume.Education.school || ' 请填写学校'}}</h3>
        <p>
            {{resume.Education.content || ' 描述'}}
        </p>
    </div>
    <div>
    <h2>项目经历</h2>
        <section v-if="filter(resume.experience).length > 0">
        
        <ul>
            <li v-for="experience in filter(resume.experience)">
                <h3>{{experience.project }}</h3>
                 {{experience.content }}
            </li>
        </ul>
        </section>
    </div>
    <div>
    <h2>获奖证书</h2>
        <section v-if="filter(resume.Trophy).length > 0">
        
        <ul>
            <li v-for="Trophy in filter(resume.Trophy)">
                <h3>{{Trophy.name }}</h3>
                 {{Trophy.content }}
            </li>
        </ul>
        </section>
    </div>
    <div class="contact">
        <h2>学习经历</h2>
        <h3>{{resume.contact.photo || ' 请填写学校'}} |  {{resume.contact.email || ' 描述'}} |
         {{resume.contact.place || ' 描述'}}
        </h3>
        
    </div>

    </div>
</template>

<style>
*{margin: 0;padding: 0;box-sizing: border-box;}
*::before{box-sizing: border-box;}
*::after{box-sizing: border-box}
ul,ol{list-style: none;}
a{color: inherit; text-decoration: none;}

#preview{
    padding: 16px 24px ;
}
h1{
    margin: 8px 0;
}
.city{
    padding: 8px 0;
}
.work{
    padding: 24px 0;
}

</style>
<script>
    export default {
        props: [ 'resume'],
        methods:{
            filter(array){
                return array.filter(item=> !this.isEmpty(item))
            },
            isEmpty(object){ //只要有一个value 不是falsy，就返回false
            let empty = true
            for(let key in object){
                if(object[key]){
                    empty = false
                    break
                }
            }
            return empty  
        }
        }  //找出非空对象
    }
</script>