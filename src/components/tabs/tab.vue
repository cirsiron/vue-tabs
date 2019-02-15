<script>
export default {
    name: 'Tab',
    props: {
        index: {
            type: [String, Number],
            require: true
        },
        label: {
            type: String,
            default: 'tab'
        }
    },
    computed: {
        active() {
            return this.$parent.value === this.index;
        }
    },
    methods: {
        handleClick() {
            this.$parent.onChange(this.index);
        }
    },
    mounted() {
        this.$parent.panes.push(this);
    },
    render() {
        const tab = this.$slots.label || <span>{this.label}</span>;
        const classNames = {
            tab: true,
            active: this.active
        }
        return (
            <li class={classNames} on-click = { this.handleClick }>
                {tab}
            </li>
        )
    }
}
</script>

<style scoped>
.tab {
    list-style: none;
  line-height: 40px;
  margin-right: 30px;
  position: relative;
  bottom: -2px;
  cursor: pointer;
  
}

  .tab.active {
      border-bottom: 2px solid blue;
  }
  .tab:last-child {
    margin-right: 0;
  }
  
</style>