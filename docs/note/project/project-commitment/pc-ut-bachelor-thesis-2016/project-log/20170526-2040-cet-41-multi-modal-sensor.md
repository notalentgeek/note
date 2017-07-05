* State of the Art table definition.
    * Commercial project refers to the implementations those are ever sold to end-consumer as the thing itself rather as a donation or a pledge.
    * DIY project refers to the implementations those can be easily made with highly available components. Spinner is not listed as DIY project because it asked for commercial support and corporate sponsorship to develop its machine learning algorithm. Especially the latter part, asking for sponsor from a company is not something that most of people can easily do.
    * Research project refers to the implementations those are one of deliverables from a research project.
    * Sensor refers to which kind of data each implementations can get.
    * Wireless communication refers to the wireless communication method on each of implementations.
    * There are cross sections between wireless communications and sensors. Some wireless communication can be used to sense presence (infrared, RF) and some others to sense proximity (Bluetooth). Classification on sensor means to transfer real-life physical data into discrete world. Whereas, classification on wireless communication means as a method used to transfer digital data between devices without physically connecting the devices.
    * Documentation refers to any documented informations to  make the implementations. These are all about electronics and software aside from the research paper.
* This section is about sensor and multi-modal sensors.
    * Insert quotation from Prelude To The Foundation here.
    * In this project, I see that there are two classifications for sensor.
    * There are traditional sensors like photo resistor that at most can only measure light intensity.
    * There are multi-modal sensors as well.
    * Multi-modal sensors usually offers more than one measurement.
    * And the result from multi-modal sensor could be both qualitative and quantitative data.
    * Examples of multi-modal sensors are things like audio recorder and video camera.
    * There are a lot of features that can be extracted from audio or video.
    * For example pitch and volume can be inferred from incoming audio, while from video light intensity and motion can be detected.
    * To get the quantitative aspect from these sensor, additional layer of processing is necessary.
    * Most of the time these are done at software level, for instance the usage of computer vision framework like OpenCV to do image processing.
    * Although the multi-modal sensors are very flexible, they have a lot of foot prints. Audio and video files take thousands bytes compared to data from traditional sensors that (usually an integer) only takes 8 bytes in 64 bits system. And not all available informations from those audios or videos will be used. As inferred from the development of Sociometric Badge __*(insert reference from the Sociometric Badge main research paper)*__, the data produced from multi-modal sensor can be further dumbed down in size, thus only necessary informations are saved. However, this means there will be system that has fast enough enough processing power and plenty of volatile memories. These are not the qualities of wearable devices, since even flag ship smart phones will have difficulties to extract data from audio and videos.
* There are two solutions for managing data from multi-modal sensor: to store the data as it is or to strip the multi-modal sensor data during the run-time. The former requires big static memories, while the latter needs faster CPU and more RAM. From this table it is known that at least XX bytes are necessary to store data per day __*(insert table from the general lifelogging paper, the table that shows on how big data will produced annually from a lifelogging activities)*__. To put into perspective, a multi-modal only social device like Memoto/Narrative Clip offers 8 gigabytes on board memory, however it received the incoming data as it is without any further operation.ut any further operation.