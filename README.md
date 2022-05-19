# Rv Adapter
  
  
  class CustomAdapter(var activity: Activity, var list: List<Any>, val click: ((Any) -> Unit)? = null) : RecyclerView.Adapter<CustomAdapter.VH>() {
    override fun onBindViewHolder(holder: VH, pos: Int) {
        val bind = holder.binding
        val data = list[pos]



        bind.root.setOnClickListener {
            click?.invoke(data)
        }
    }

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int) = VH(RvCustomBinding.inflate(LayoutInflater.from(parent.context)))
    class VH(var binding: RvCustomBinding) : RecyclerView.ViewHolder(binding.root)

    override fun getItemCount() = list.size
}
