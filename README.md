STM32_FileTransferDMA_IdleLine

Codigo de exemplo de transferencia de arquivo pela USART2 usando DMA e Idle Line, onde a interrupcao identifica automaticamente a finalizacao do recebimento do buffer por um timeout de recebimento, acionando a interrupcao e podendo entao realizar o tratamento do buffer.

Foi utilizado DMA Circular nessa implementacao, para que o IdleLine funcione corretamente pois o envio de arquivo pode ser particionado dependendo de onde é transmitido, e o particionamento do arquivo ocasiona em um pequeno delay de um para o outro que ocasiona na interrupcao antes do recebimento total. Com o DMA circular, mesmo com essa interrupcao sendo ocasionado a cada particao do arquivo recebido, é possivel continuar o recebimento e durante as interrupcoes realizar a tratativa do buffer tenporario para formacao do arquivo final.
