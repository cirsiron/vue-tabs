<script>
export default {
    name:'TabConatiner',
    props: {
        panes: {
            type: Array,
            required: true
        }
    },
    render() {

        const contents = this.panes.map((pane) => {
            return pane.active ? pane.$slots.default :  null;
        })

        return (
            <div class='tabs-content'>
                {contents}
            </div>
        )
    }
}
</script>