Podemos simplesmente usar o [audio] com [source] [type],  junto com o parâmetro [controls] (para fazer a ferramenta do áudio aparecer) e o [preload], em que o parâmetro recomendado é o "metadata", pois ele mostra as minutagens do áudio mas sem baixa-lo por completo, só se o usuário quiser ouvi-lo.

ex: [audio src="midia/audio.mp3" controls preload="metadata"]

mas se quiser colocar vários tipos de fonte, podemos:

Usar o [audio] com o preload e controls
colocar as tags [source], e alterar o type conforme o tipo do arquivo. Os tipos são: MP3, OGG e WAV.