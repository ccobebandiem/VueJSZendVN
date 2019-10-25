<template>
  <div class="demo-slot">
    <comp-tabs title="Tieu de cua tab">
      <ul class="tabs-header">
        <li
          v-for="(item, index) in tabsHearder"
          v-on:click="setActiveTab(index)"
          v-bind:class="{ active: tabActive == index }"
          v-bind:key="index">{{ item.text }}
        </li>
      </ul>
      <div class="tab-content tab1" v-if="tabActive === 0">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Mollitia neque quia sint tenetur. Id neque nesciunt
          nulla possimus vel veniam.</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ad aut distinctio, eaque eos, exercitationem fuga
          harum id maiores modi mollitia neque nisi obcaecati perferendis provident quae quo totam velit?</p>
      </div>
      <div class="tab-content tab2" v-else-if="tabActive === 1">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aspernatur blanditiis commodi consequatur ex labore
          possimus quae quis tempore vel. Asperiores atque aut beatae deleniti deserunt eius est exercitationem, fugit
          harum illo incidunt maiores maxime natus non, numquam omnis quo sapiente sed similique voluptas voluptate
          voluptatem voluptatibus? Aliquid non quaerat ut?</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet consectetur corporis cupiditate earum facere
          facilis inventore laboriosam libero maiores modi perferendis quae quasi, repellat tempora veniam! Dolores
          error iusto tenetur!</p>
      </div>
      <div class="tab-content tab3" v-else-if="tabActive === 2">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequuntur dolorem itaque minima non placeat
          provident qui? Alias autem dignissimos dolores explicabo iure maxime vel. Aperiam delectus dolores eos, error
          eveniet ipsam ipsum, pariatur, possimus rem suscipit tempora tenetur totam? Sint!</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magni, tenetur.</p>
      </div>
      <div class="tab-content tab4" v-else-if="tabActive === 3">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A autem corporis dolore earum incidunt magni neque
          numquam, placeat possimus provident quia quod recusandae, saepe sed, sunt tempore voluptatum. Aliquam,
          iure.</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus, consectetur.</p>
      </div>
      <div class="tab-content tab5" v-else-if="tabActive === 4">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsam, temporibus.</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto asperiores cupiditate delectus dicta,
          eius eos neque quidem tempore ullam vero.</p>
        <p>Loipsum dolor sit amet, consectetur adipisicing elit. Accusantium dolore ea eligendi fugiat fugit ipsum
          laudantium maxime modi mollitia omnis possimus rem repellendus similique sit suscipit, tenetur vero
          voluptates? Tempore.</p>
        <p>Ab accusamus, atque, dignissimos dolore ducimus eos ex excepturi fugit harum illum inventore iure iusto
          laboriosam libero magni maiores minima nulla officia officiis optio porro recusandae sed similique
          voluptatibus voluptatum!</p>
      </div>
      <div class="tab-content tab6" v-else>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Modi, ut!</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A accusamus ad, aliquam aliquid architecto
          aspernatur corporis cumque dolorem doloremque earum eos est et eum, eveniet facere incidunt ipsum iure
          laudantium libero, non nostrum odio officia pariatur quae quas qui quibusdam quisquam ratione sequi sit soluta
          sunt tempore temporibus ullam velit voluptatibus voluptatum! Ab doloribus facere maiores quibusdam
          voluptatibus. Aliquam cum cupiditate eius id illum obcaecati officiis quasi? Cupiditate dignissimos ducimus
          eos ex id non officiis perferendis reiciendis sapiente tempore, temporibus ut voluptatibus voluptatum.
          Consequatur doloremque illo ipsam maxime optio! Et non, quasi. At atque magni nemo non odio quo similique.</p>
      </div>
    </comp-tabs>
  </div>
</template>

<script>
    import CompTabs from "./CompTabs";

    export default {
        name: "demo-slot",
        components: {
            CompTabs
        },
        data() {
            return {
                tabsHearder: [
                    {text: 'Tab1'},
                    {text: 'Tab2'},
                    {text: 'Tab3'},
                    {text: 'Tab4'},
                    {text: 'Tab5'},
                    {text: 'Tab6'},
                ],
                tabActive: 0,
            }
        },
        methods: {
            setActiveTab(index) {
                this.tabActive = index;
            }
        }
    }
</script>

<style scoped>
  .demo-slot {
    margin-top: 100px;
    padding: 100px 30px;
    border: 1px solid #3498db;
  }
</style>
