# GZipZipper
console C# zipp application based on GZip
<br /><b>version 0.0.1.0</b> <br /> <br />
Multithreading zipping algorithm: <br />
  * Separated thread consequentially read file by sized blocks and push tem to sourse data queue. <br />
  * According to CPU cores count creates threads, whicth take data blocks from queue of sourse data, archived them with gzip, numerate them and push to archive data queue. <br />
  * Because fragmented zip thread impossible to unzip in unusual way, information about blocks lenght writes in addition. <br />
<br /> *Idea:* <br />
   If we compress bad compressed data, add a flag to indicate if we whould or not to decompress data. <br /> 
   Add a separate thread to check next data block in qeue and if it found to push it to outgoing thread. <br />
<br /> Note: <br />
  - Paralleling decompression wasnt inmplemented, because this operation uses very rare in working with backups. If its needed, imlements trivial base on algorithm of parallel compressing. <br />
<br /><b>version 0.0.2.0</b> <br /> <br />
  * Created separated classes for compressor's working threads. <br />
  * Sleeps in threads replaced with auto reset events. <br /> 
  * Added exception handles in work thread classes. <br />
  * Many variable in compressor class were make static for more convinient using.	<br />
<br /> *Idea:* <br />
  To add in thread compreser class counter, to check if we have enought memory for perform. <br />
