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
    
# common deps

    //sdp
    implementation 'com.intuit.sdp:sdp-android:1.0.6'
    
    //retrofit2
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
    
    //interceptor
    implementation 'com.squareup.okhttp3:logging-interceptor:4.9.1'
    
    //gson
    implementation 'com.google.code.gson:gson:2.8.9'
    
    //Glide
    implementation 'com.github.bumptech.glide:glide:4.13.0'
    annotationProcessor 'com.github.bumptech.glide:compiler:4.13.0'
