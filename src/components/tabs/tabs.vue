<script>
import TabContainer from './tab-container.vue';

export default {
    name: 'Tabs',
    props: {
        value: {
            type: [String, Number],
            required: true
        }
    },
    components: {
        TabContainer
    },
    data() {
        return {
            panes: []
        }
    },
    render() {
        return (
            <div class='tabs'>
                <ul class='tabs-header'>
                    {this.$slots.default}
                </ul>
                
                <tab-container panes={this.panes}/>
            </div>
        )
    },
    methods: {
        onChange(index) {
            this.$emit('change', index);
        }
    }
}
</script>

<style>
.tabs-header {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  border-bottom: 2px solid #ededed;
}
</style>
