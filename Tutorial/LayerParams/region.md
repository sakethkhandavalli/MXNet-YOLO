# Region Layer
## Params (default value)
#### black params are in yolo-voc.cfg
__coords__ (4) = 4  
__classes__ (20) = 20  
__num__ (1) = 5 : layer.n, number of anchors  
log (0)  
sqrt (0)  
__softmax__ (0) = 1  
background (0)  
max (30) : max number of boxes  
__jitter__ (.2) = .3 (data augmentation) 
__rescore__ (0) = 1  
__thresh__ (.5) = .6  
classfix (0)  
__absolute__ (0) = 1  
__random__ (0) = 1 : for multi scale training. every 10 epoch randomly choose a new size followinf multiples of 32 {320, ..., 608}. ATTENTION: if (get_current_batch(net)+200 > net.max_batches) dim = 608;  
__coord_scale__ (1) = 1  
__object_scale__ (1) = 5  
__noobject_scale__ (1) = 1  
mask_scale (1)  
__class_scale__ (1) = 1  
__bias_match__ (0) = 1  
tree (0) : tree file for l.softmax_tree  
map (0)  
__anchors__ (0) = 1.3221, 1.73145, 3.19275, 4.00944, 5.05587, 8.09892, 9.47112, 4.84053, 11.2364, 10.0071 : str of anchors separated by comma (,)  
## Internals
type, n, batch, h, w, c, out_w, out_h, out_c, cost(ptr), biases(ptr), bias_updates(ptr), outputs, inputs, truths, delta(ptr), output(ptr)  
* n: number of anchor
* cost: loss
* c, out_c: n x (classes + coords + 1)
* bias: float array of length 2n
* inputs = outputs
* truths = 30 x (coords+1) (keep top 30 scores)
* delta : float array of length batch x outputs (gradient)
* output: float array of length batch x outputs
