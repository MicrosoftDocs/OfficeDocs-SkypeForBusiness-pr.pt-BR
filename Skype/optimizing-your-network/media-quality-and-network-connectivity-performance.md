---
title: "Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "Este tópico define um conjunto de exigências de desempenho de rede para os serviços do Skype for Business Online e como você pode usar a Internet ou a Rota Expressa para estabelecer conectividade entre sua rede e o Skype for Business Online com base na avaliação de sua conectividade de rede. Se você optou por instalar a Rota Expressa do Azure para obter conectividade dedicada com o Office 365, este documento também fornece diretrizes sobre como planejar suas conexões da Rota Expressa em diferentes cenários de implantação do Skype for Business Online."
---

# Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online

Este tópico define um conjunto de exigências de desempenho de rede para os serviços do Skype for Business Online e como você pode usar a Internet ou a Rota Expressa para estabelecer conectividade entre sua rede e o Skype for Business Online com base na avaliação de sua conectividade de rede. Se você optou por instalar a Rota Expressa do Azure para obter conectividade dedicada com o Office 365, este documento também fornece diretrizes sobre como planejar suas conexões da Rota Expressa em diferentes cenários de implantação do Skype for Business Online.
  
A qualidade das mídias em tempo real (áudio, vídeo e compartilhamento de aplicativos) por meio de IP é bastante afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídias com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede de sua empresa e o Skype for Business Online. A melhor maneira de se conseguir isso é configurando sua rede interna e a conectividade de nuvem com base na capacidade de sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
A Rota Expressa do Azure não é um requisito para os serviços do Office 365 que incluem o Skype for Business Online. Entretanto, a Rota Expressa do Azure é uma das opções de implantação disponíveis para assegurar que a conectividade com o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídias do Skype for Business Online.
  
> [!TIP]
> Embora este tópico forneça diretrizes gerais sobre o desempenho de rede, uma diretriz completa sobre avaliação de rede está fora do escopo deste documento. Para obter uma lista dos parceiros do Skype for Business Online que podem ajudá-lo com as avaliações de desempenho de rede como parte de uma avaliação completa de rede, acesse [Soluções de Parceiros do Skype for Business](http://partnersolutions.skypeforbusiness.com/). 
  
## Requisitos de conectividade de rede para o Skype for Business Online

### Fatores que afetam a qualidade das mídias do Skype for Business Online

Há vários fatores que contribuem com a qualidade das mídias em tempo real do Skype for Business Online (áudio, vídeo e compartilhamento de aplicativos), que incluem os dispositivos que são usados, o ambiente e a conectividade de rede. 
  
#### Dispositivos

Em uma sessão de mídias em tempo real, dispositivos de captura e apresentação de mídias que são usados por todos os participantes, como fones de ouvido e webcams, têm grande impacto na qualidade geral do áudio e do vídeo. Dispositivos de baixa qualidade ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, os dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Embora dispositivos de áudio e vídeo certificados não sejam obrigatórios, é altamente recomendável o seu uso com o Skype for Business a fim de obter uma ótima experiência de mídias. Para obter uma lista de todos os dispositivos certificados para o Business, consulte [Telefones e dispositivos para Skype for Business](https://technet.microsoft.com/en-us/office/dn947482). Você pode usar o [Painel de qualidade de chamada do Skype for Business Online](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US), localizado no **Centro de administração do Skype for Business**, para verificar se os dispositivos em uso estão funcionando corretamente e monitorar a qualidade das mídias de áudio e vídeo.
  
> [!TIP]
> **É necessário um dispositivo certificado para obter uma ótima experiência de qualidade de mídias no Skype for Business**.
  
É importante lembrar que quaisquer dispositivos de mídia, clientes de Skype for Business e servidores do Skype for Business, por meio dos quais as mídias em tempo real fluem, introduzem um pouco de latência. A latência de processamento de dispositivo e software, junto com a latência de rede, causam um grande impacto e contribuem com a latência geral de ponta a ponta, afetando a experiência do usuário final.
  
#### Ambiente

O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter um quadro mais claro da experiência de áudio e vídeo de um usuário, use o aplicativo Skype for Business ** Ferramentas** > **Opções** > **Dispositivo de Áudio** ou **Dispositivo de Vídeo** para efetuar alterações no dispositivo em uso e personalizar suas configurações. Você também pode verificar a qualidade de áudio de uma chamada clicando em ** Verificar Qualidade da Chamada**. Quando você clica em **Verificar Qualidade da Chamada**, é possível reportar a qualidade e os problemas encontrados na chamada de teste.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Rede

A qualidade das mídias em tempo real por meio da rede IP é muito afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:
  
- **Latência** Este é o tempo levado para obter um pacote IP do ponto A ao B na rede. Esse atraso de propagação na rede está basicamente vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional ocasionada por vários roteadores intermediários. A latência é medida como unidirecional ou RTT (Tempo de Viagem de Ida e Volta).
    
- **Perda de pacote** Isso costuma ser definido como uma porcentagem de pacotes que são perdidos em um determinado intervalo de tempo. A perda de pacote afeta diretamente a qualidade do áudio  desde a perda de pacotes pequenos e individuais que praticamente não causam impacto até perdas de intermitência consecutivas que ocasionam a perda total de áudio.
    
- **Tremulação de chegada entre pacotes ou simplesmente tremulação** Esta é a alteração média no atraso entre pacotes sucessivos. Os softwares VoIP mais modernos, incluindo o Skype for Business, podem adaptar alguns níveis de tremulação por meio de armazenamento em buffer. Um participante percebe os efeitos da tremulação somente quando ela excede o armazenamento em buffer.
    
> [!NOTE]
>  O armazenamento em buffer da tremulação aumenta a latência de ponta a ponta.
  
Com muitas sessões simultâneas de mídias em tempo real do Skype for Business Online, bem como outro tráfego de rede gerado por outros serviços do Office 365 e outros aplicativos corporativos, é essencial verificar se há largura de banda suficiente em todo o caminho da rede que conecta sua rede com o serviço do Skype for Business Online para evitar congestionamento da rede e garantir uma excelente qualidade de mídias em tempo real (áudio, vídeo e compartilhamento de aplicativos). 
  
#### Como implementar a QoS (Qualidade de Serviço) em redes congestionadas

Além disso, o congestionamento de tráfego em uma rede afetará muito a qualidade da mídia. Para permitir que pacotes de áudio e vídeo viagem mais rapidamente pela rede e sejam priorizados no outro tráfego de uma rede congestionada, a QoS pode ser utilizada para fornecer uma excelente experiência para o usuário final em termos de áudio e vídeo.
  
A QoS permite que você atribua prioridades mais altas aos pacotes de rede que estão transmitindo dados de áudio ou vídeo. Ao atribuir uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo trafegarão pela rede com maior rapidez e com menos interrupção do que as sessões de rede que envolvem transferências de arquivo, navegação na Web ou backups de banco de dados. Isso ocorre porque, por padrão, é atribuído o "melhor esforço" aos pacotes de rede utilizados para as transferências de arquivo ou backups de banco de dados como uma prioridade e o congestionamento de rede não causará grande impacto. Se você não atribuir uma prioridade mais alta aos pacotes de mídias (áudio, vídeo e compartilhamento de aplicativo) e também deixá-los atribuídos como "melhor esforço", eles também serão processados com todos os outros tráfegos da rede. Dependendo da quantidade de congestionamento da rede, isso provavelmente fará com que os usuários tenham uma experiência geral de baixa qualidade de áudio e vídeo.
  
É altamente recomendável que você implemente a QoS em sua rede para assegurar que o congestionamento de rede não cause impacto. No entanto, todos os pontos de extremidade da rede devem dar suporte à QoS. Isso significa que todos os pontos de extremidade devem aceitar a marcação e a priorização de pacotes da QoS. Os serviços do Skype for Business Online aceitam a marcação e a priorização da QoS na rede da Microsoft. Entretanto, o tráfego que é roteado por uma conexão pública, como a Internet da rede de sua empresa para a rede da Microsoft, não preserva as marcações e a priorização de pacotes da QoS. As conexões particulares de sua rede com o Office 365 que usam o [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) oferecem uma solução de implantação que preserva as marcações e a priorização de pacotes da QoS que, por sua vez, aumentam a qualidade geral de áudio e vídeo para seus usuários finais.
  
## Requisitos de desempenho de rede para conexão com o Skype for Business Online
<a name="bk_NetworkPerf"> </a>

As mídias em tempo real do Skype for Business trafegam por diferentes dispositivos, aplicativos clientes, software de servidor e em diversas redes. A latência de ponta a ponta de mídias em tempo real é a quantidade total de latência introduzida por todos os componentes e segmentos de rede. A qualidade da conexão de rede de ponta a ponta é determinada pelo segmento de rede que possui a pior qualidade. Esse segmento atua como um gargalo para esse tráfego de rede.
  
O diagrama a seguir ilustra o fluxo de áudio unidirecional em uma conferência de um participante do Skype for Business com outro.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Nesse cenário de conferência, o caminho das mídias consiste nos seguintes segmentos de rede:
  
1. **Conexão do Usuário 1 com a borda da rede da Microsoft** Isso costuma incluir uma conexão de rede como WiFi ou Ethernet, a conexão WAN do Usuário 1 com o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão da Internet de sua borda de rede com a borda de rede da Microsoft.
    
2. **Conexão na rede da Microsoft** Essa conexão ocorre entre o Microsoft Edge com o data center do Skype Business Online, onde os servidores de Conferência A/V são utilizados.
    
3. **Conexão na rede da Microsoft** Essa conexão ocorre entre o data center do Skype for Business Online e a borda de rede da Microsoft.
    
4. **Conexão da borda de rede da Microsoft com o Usuário 2** Isso inclui a conexão de Internet de sua borda de rede com a borda de rede da Microsoft, a conexão WAN do Usuário 2 com o ponto de saída da Internet (sua borda de rede) e a conexão de rede com WiFi ou Ethernet.
    
O diagrama a seguir mostra a divisão dos componentes e os segmentos de rede de uma chamada PSTN do Skype for Business Online:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Em um cenário de chamada PSTN, o caminho das mídias consiste nos seguintes segmentos de rede:
  
1. **Conexão de um chamador cliente do Skype for Business com a borda da Rede da Microsoft** Isso geralmente inclui uma conexão de rede como WiFi ou Ethernet, a conexão WAN do chamador cliente do Skype for Business com o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão com a Internet de sua borda de rede com a borda de rede da Microsoft.
    
2. **Conexão na rede da Microsoft** Essa conexão ocorre entre o Microsoft Edge com o data center do Skype for Business Online, onde um Servidor de Mediação é utilizado.
    
3. **Conexão na rede da Microsoft** Essa conexão ocorre entre o data center do Skype for Business Online e a borda de rede da Microsoft.
    
4. **Conexão entre o Microsoft Network e os parceiros de provedores de serviço PSTN** Essa é uma conexão que existe para estabelecer uma chamada PSTN do cliente Skype for Business que está fora da rede da Microsoft.
    
### Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft
<a name="bk_SfBClienttoEdge"> </a>

Para obter uma ótima qualidade de mídias no Skype for Business, as seguintes metas ou limites de métricas de desempenho de rede são necessários para uma conexão a partir da rede de sua empresa com a borda de rede da Microsoft. Este segmento da rede inclui sua rede interna, ou seja, todas as conexões de WiFi e Ethernet, qualquer tráfego local a local da empresa por meio de uma conexão WAN, por exemplo, MPLS (Multiprotocol Label Switching), bem como a Internet ou as conexões de parceiros da Rota Expressa com a borda de rede da Microsoft.
  
> [!CAUTION]
> **A conectividade entre um cliente Skype for Business em sua rede da empresa com os serviços do Office 365 deve atender a esses seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Meta** <br/> |
|Latência (unidirecional)  <br/> |< 50ms  <br/> |
|Latência (RTT ou Tempo de Viagem de Ida e Volta)  <br/> |< 100ms  <br/> |
|Perda de pacote de intermitência  <br/> |<10% durante qualquer intervalo de 200ms  <br/> |
|Perda de pacote  <br/> |<1% durante qualquer intervalo de 15s  <br/> |
|Tremulação de chegada entre pacotes  <br/> |<30ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |<0.05% pacotes fora de ordem  <br/> |
   
 **Outros requisitos de meta de desempenho:**
  
- A rede da Microsoft tem mais de 160 localizações de borda no mundo todo. Trabalhamos com os principais ISPs (Provedores de Serviço de Internet) do mundo todo por meio desses sites de borda. A meta de métrica de latência supõe que o site ou sites da empresa e as bordas da Microsoft estão no mesmo continente.
    
- O site ou sites da empresa para conexão de borda de rede da Microsoft inclui(em) o primeiro acesso de rede de salto, que pode ser WiFi ou outra tecnologia sem fio. 
    
- A meta de desempenho de rede supõe uma largura de banda adequada e/ou planejamento de qualidade de serviço. Em outras palavras, isso se aplica diretamente ao tráfego de mídias em tempo real do Skype for Business quando a conexão de rede está sob uma carga de pico.
    
### Requisitos de desempenho de rede de sua borda de rede para a borda de rede da Microsoft
<a name="bk_YourNetworkEdge"> </a>

A seguir são apresentadas as metas ou limites de desempenho de rede exigidos para a conexão entre sua borda de rede e a borda de rede da Microsoft. Este segmento da rede exclui a rede interna ou WAN do cliente e serve como diretriz durante o teste de tráfego de rede que é enviado pela Internet ou por meio de uma rede de parceiro de Rota Expressa e também pode ser utilizado durante a negociação de um SLA (Contrato de Nível de Serviço) de desempenho com seu provedor de Rota Expressa.
  
> [!CAUTION]
> **A conectividade entre a borda de rede de sua empresa com a borda de rede da Microsoft deve atender aos seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Meta** <br/> |
|Latência (unidirecional)  <br/> |< 30ms  <br/> |
|Latência (RTT)  <br/> |< 60ms  <br/> |
|Perda de pacote de intermitência  <br/> |<1% durante qualquer intervalo de 200 ms  <br/> |
|Perda de pacote  <br/> |<0,1% durante qualquer intervalo de 15s  <br/> |
|Tremulação de chegada entre pacotes  <br/> |<15ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |<0.01% pacotes fora de ordem  <br/> |
   
 **Outros requisitos de meta de desempenho:**
  
- A meta de desempenho exige conexão entre qualquer borda de rede de sua empresa e sua borda de rede da Microsoft mais próxima, que devem estar no mesmo continente.
    
- A meta de desempenho de rede supõe que já exista largura de banda adequada e/ou planejamento de qualidade de serviço. Isso também se aplica ao tráfego de mídias em tempo real do Skype for Business quando a conexão de rede está sob uma carga de pico. Para obter a largura de banda adequada e o planejamento de QoS, consulte [Rota Expressa e QoS no Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## Como avaliar o desempenho da rede
<a name="bk_NetworkPerf"> </a>

Para medir o desempenho real da rede, especialmente no que diz respeito à latência e à perda de pacotes, de qualquer site de rede da empresa para uma borda de rede, você pode usar ferramentas como ping, testar com base em um conjunto de serviços de Media Relay do Skype for Business executado de uma borda da Microsoft e sites de data center. 
  
Para testar as conexões de Internet com a rede da Microsoft, é recomendável que você teste com base nos VIPs de Media Relay do Skype for Business a seguir. O  *Anycast VIP*  resolverá um endereço IP de um Media Relay em um site de borda da Microsoft que esteja mais próximo ao local do teste.
  
||||
|:-----|:-----|:-----|
|**Endereço IP** <br/> |**Tipo** <br/> |**Localização** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |Anycast IP no mundo todo  <br/> |
   
 **A seguir são apresentadas algumas recomendações de alto nível a serem seguidas ao avaliar o desempenho da rede:**
  
- Você deve avaliar sua rede interna, bem como as conexões com o Office 365.
    
- Você deve avaliar e coletar dados de todas as suas redes por um período prolongado. Recomendamos que você execute testes de desempenho da rede por no mínimo uma semana, assim, é possível verificar os padrões de uso de todos os dias e horários comerciais. Esse procedimento revelará os períodos de pico.
    
- Obtenha várias amostras de avaliações de desempenho da rede. Recomendamos uma avaliação a cada 10 minutos, a ser feita dentro da empresa, durante todo o período em que você estiver coletando os dados. Para comparar os requisitos de desempenho de rede do Skype for Business Online, pegue o valor da avaliação do 90o percentil desse conjunto de dados de amostra. 
    
- O desempenho da rede deve ser avaliado continuamente. O uso da rede varia com o decorrer do tempo devido a mudanças no padrão de uso, novos aplicativos baseados na empresa, que usam grande quantidade de largura de banda, e mudanças nas localizações físicas e organizacionais da empresa. É importante que você monitore continuamente o desempenho da rede com base nesses requisitos de desempenho de rede e metas/limites e efetue ajustes oportunamente para garantir a melhor qualidade de mídias em tempo real. 
    
## Como medir o desempenho da rede usando VMs do Azure
<a name="bk_NetworkPerf"> </a>

Em vez de fazer testes baseados nos sites de borda de rede da Microsoft, existem soluções de avaliação da rede de clientes e parceiros do Skype for Business que utilizam a configuração de teste para serviços na nuvem do Microsoft Azure. Nessas soluções, as ferramentas de avaliação da rede testam a latência, a perda de pacotes e tremulação em pontos de extremidade personalizados configurados como um serviço na nuvem do Azure. Como resultado, o tráfego de rede de teste viaja por um segmento de rede adicional, que é a conexão na rede da Microsoft entre as bordas da rede e data centers do Azure que hospedam o serviço de avaliação da rede.
  
Para essas soluções de avaliação da rede com base em serviços de teste hospedados pelo Azure. Recomendamos a execução da avaliação da rede dentro do país e/ou região. Por exemplo, para sites de clientes no leste dos EUA, a avaliação deve ser realizada em uma instância de serviço de teste hospedada na região do data center do Azure do leste dos EUA. 
  
Veja abaixo as metas de latência (tempo de resposta) para a configuração de avaliação da rede baseada em serviços do Azure. As metas de latência unidirecionais serão a metade das metas de tempo de resposta correspondentes. As metas de perda de pacotes e tremulação permanecem iguais às definidas para o teste baseado em Media Relay do Skype.
  
|||||
|:-----|:-----|:-----|:-----|
|**Região do cliente** <br/> |**Região do Azure** <br/> |**Sua borda da rede - RTT (tempo de resposta) do Azure** <br/> |**Seu site - RTT do Azure** <br/> |
|Centro dos EUA  <br/> |Centro dos EUA  <br/> |99  <br/> |139  <br/> |
|Leste dos EUA  <br/> |Leste dos EUA  <br/> |86  <br/> |126  <br/> |
|Centro-Norte dos EUA  <br/> |Centro-Norte dos EUA  <br/> |97  <br/> |137  <br/> |
|Centro-Sul dos EUA  <br/> |Centro-Sul dos EUA  <br/> |94  <br/> |134  <br/> |
|Oeste dos EUA  <br/> |Oeste dos EUA  <br/> |94  <br/> |134  <br/> |
|Havaí, EUA  <br/> |Oeste dos EUA  <br/> |116  <br/> |156  <br/> |
|Centro do Canadá  <br/> |Centro do Canadá  <br/> |138  <br/> |178  <br/> |
|Leste do Canadá  <br/> |Leste do Canadá  <br/> |131  <br/> |171  <br/> |
|Norte da Europa  <br/> |Norte da Europa  <br/> |99  <br/> |139  <br/> |
|Oeste da Europa  <br/> |Oeste da Europa  <br/> |95  <br/> |135  <br/> |
|Leste da Ásia  <br/> |Leste da Ásia  <br/> |118  <br/> |158  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |97  <br/> |137  <br/> |
|Leste do Japão  <br/> |Leste do Japão  <br/> |111  <br/> |151  <br/> |
|Oeste do Japão  <br/> |Oeste do Japão  <br/> |118  <br/> |158  <br/> |
|Sul do Brasil  <br/> |Sul do Brasil  <br/> |70  <br/> |110  <br/> |
|Leste da Austrália  <br/> |Leste da Austrália  <br/> |124  <br/> |164  <br/> |
|Sudeste da Austrália  <br/> |Sudeste da Austrália  <br/> |124  <br/> |164  <br/> |
|Centro da Índia  <br/> |Centro da Índia  <br/> |103  <br/> |143  <br/> |
|Sul da Índia  <br/> |Sul da Índia  <br/> |103  <br/> |143  <br/> |
|Oeste da Índia  <br/> |Oeste da Índia  <br/> |103  <br/> |143  <br/> |
|Leste da China  <br/> |Leste da China  <br/> |120  <br/> |160  <br/> |
|Norte da China  <br/> |Norte da China  <br/> |120  <br/> |160  <br/> |
   
## Qualidade das mídias e Rota Expressa
<a name="bk_NetworkPerf"> </a>

O Azure ExpressRoute para Office 365 é uma conexão de rede dedicada para conexão com o Office 365. Ele oferece aos clientes controle sobre o caminho usado pelo tráfego de rede do Office 365. Eles não precisam mais ficar preocupados com o roteamento imprevisível que ocorre na Internet, onde os dados são transmitidos por operadoras, fornecedores e ISPs desconhecidos. O tráfego de rede transmitido pelo ExpressRoute é enviado diretamente pela rede do parceiro do ExpressRoute para a rede da Microsoft. Isso permite que os clientes tratem o Office 365 como se ele estivesse localizado em seu próprio data center externo com uma conexão dedicada.
  
A Rota Expressa do Azure está disponível para todas as ofertas de licenciamento do Office 365. No entanto, o Complemento Premium da Rota Expressa do Azure é exigido para o Office 365 para habilitar o roteamento global. Os clientes do Office 365, com pelo menos 500 usuários, que estão implementando a Rota Expressa, podem obter o  *Complemento Premium da Rota Expressa*  gratuitamente.
  
### A Rota Expressa é necessária para a boa qualidade das mídias?

A Rota Expressa do Azure não é um requisito para a obtenção de uma excelente qualidade de mídia no Skype for Business Online. Entretanto, ela é uma das opções de implantação que ajudam você a assegurar que sua conectividade de nuvem atenda às metas ou limites de desempenho de rede do Skype for Business.
  
O Office 365 é um serviço de alto desempenho e seguro que usa a Internet. Continuamos investindo em novos recursos de segurança e em nós de borda regionais a fim de melhorar continuamente a segurança e o desempenho. A Rota Expressa do Azure não é um requisito para os serviços do Office 365 que incluem o Skype for Business Online. A Rota Expressa do Azure é uma das opções de implantação disponível para assegurar que a conectividade com o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garantir a melhor experiência de qualidade de mídias do Skype for Business Online.
  
Para obter qualidade de mídias no Skype for Business Online, é importante que a conexão entre os sites de sua empresa e as bordas de rede da Microsoft atendam às metas de desempenho contidas nos [Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) e que a conexão entre suas bordas de rede e as bordas de rede da Microsoft atendam às metas de desempenho contidas nos[Requisitos de desempenho de rede de sua borda de rede para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge). 
  
Também é importante que a conectividade de rede física de sua empresa, incluindo sua rede interna e a capacidade de conectividade de nuvem acomodem o volume de pico do tráfego das mídias. A Rota Expressa do Azure é uma das muitas maneiras de ajudar os clientes assegurarem que sua conectividade de nuvem do Skype for Business Online atenda a todos esses requisitos de desempenho.
  
### A Rota Expressa é necessária para o SLA de qualidade de voz?

Não, a Rota Expressa não é necessária para o SLA de qualidade de voz do Skype for Business Online. O [SLA de qualidade de voz do Skype for Business Online ](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) é aplicável a qualquer chamada qualificada estabelecida por qualquer usuário de serviço de voz do Skype for Business Online com a licença e assinatura corretas que permitam que o usuário faça qualquer tipo de chamada VoIP ou PSTN. Um SLA de qualidade de voz deve tratar de todas as condições a seguir:
  
- Chamadas de telefones IP certificados pela Microsoft.
    
- Conexões Ethernet com fio.
    
- Problemas de qualidade de voz devido a problemas com o Microsoft Network.
    
> [!NOTE]
> O SLA de qualidade de voz exclui chamadas em que a baixa qualidade da chamada é ocasionada por problemas em redes que não são da Microsoft, incluindo o parceiro da Rota Expressa e outras redes. 
  
### Internet ou Rota Expressa do Azure?

Antes de tomar uma decisão sobre as opções de conectividade de rede para o Skype for Business Online, os clientes devem avaliar sua rede e conectividade atuais de Internet com base nos requisitos de desempenho de rede descritos em [Requisitos de desempenho de rede para conexão com o Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf).
  
Se o desempenho da rede pela atual conexão de Internet estiver configurado com capacidade suficiente para o período de pico e se ele atende aos requisitos de desempenho de rede dos sites para as bordas de rede da Microsoft e de suas bordas de rede para as bordas de rede da Microsoft, você pode continuar usando sua conectividade de Internet atual para se conectar com o Skype for Business Online.
  
Para os sites da empresa em que os requisitos de desempenho de rede não estão sendo atendidos, é altamente recomendável que você primeiramente trabalhe com os provedores de serviço de rede existentes para aprimorar o desempenho geral da rede. Entretanto, se eles não forem atendidos, o uso da Rota Expressa do Azure pode assegurar que sua conectividade de nuvem do Skype for Business Online atenda aos requisitos de desempenho de rede.
  
A Rota Expressa do Azure oferece os seguintes benefícios adicionais:
  
- Um SLA sobre a disponibilidade da conexão entre sua rede e a rede da Microsoft. A Rota Expressa tem um SLA de Disponibilidade garantida de 99.9%.
    
- Largura de banda planejada e garantida exigida para os serviços do Office 365. Você pode obter isso enviando apenas tráfego do Office 365 ou do Skype for Business usando a Rota Expressa e, depois, fazer com que todos os outros tráfegos da Internet passem por outros pontos de entrada/saída da Internet para sua rede.
    
- O ExpressRoute foi projetado para preservar as marcações de QoS do DSCP (Ponto de Código de Serviços Diferenciados) entre sua rede e a rede da Microsoft.
    
Para obter mais informações sobre a QoS e o planejamento da capacidade da Rota Expressa, consulte a [Rota Expressa e QoS no Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### Posso configurar a Rota Expressa do Azure apenas para o Skype for Business Online?

Sim. Você pode configurar a Rota Expressa do Azure para garantir uma excelente conectividade de rede a partir da rede de sua empresa somente para o Skype for Business Online. Isso fornecerá a melhor qualidade de mídias em tempo real para seus usuários, mas você poderá continuar conectando-se com os outros serviços do Office 365 pela Internet.
  
O BGP (Protocolo de Gateway de Borda) é um protocolo de roteamento na Internet que é usado para encaminhar o tráfego de rede em toda a Internet. É projetado para trocar informações de roteamento entre sistemas autônomos (AS) encontrados em toda a Internet. Os valores das comunidades BGP são marcas de atributos que podem ser aplicadas às rotas de entrada ou saída. As comunidades BGP são frequentemente usadas para sinalizar ao AS receptor qual link de saída usar para chegar a um determinado destino com base na região geográfica, no tipo de serviço ou em outros critérios.
  
Com o suporte para comunidades BGP, a Microsoft marcará os prefixos e as rotas com os valores adequados da comunidade BGP com base no serviço aos quais pertencem. A Microsoft marcará prefixos anunciados por meio de emparelhamento público e o emparelhamento da Microsoft com os valores adequados da comunidade BGP indicando a região em que os prefixos estão hospedados. Você pode contar com os valores da comunidade para tomar as decisões certas de roteamento a fim de oferecer um excelente roteamento. Você pode usar o valor da comunidade BGP do Skype for Business Online para configurar uma conexão da Rota Expressa somente para o Skype for Business Online. Para obter mais detalhes, consulte [Requisitos de roteamento da Rota Expressa](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## Cenários de conectividade da Rota Expressa para Skype for Business Online
<a name="bk_NetworkPerf"> </a>

Se, com base nas recomendações acima, você constatou que deve usar a Rota Expressa, seguem algumas recomendações sobre onde e como obter muitas conexões da Rota Expressa.
  
### Implantação somente online - site único

Se todos os seus usuários usam o serviço Skype for Business Online e se os seus escritórios estão centralizados em torno de um único local físico, ao decidir implantar a Rota Expressa do Azure, você deverá definir a conexão única de Rota Expressa entre o site de sua empresa e o local mais próximo de [emparelhamento da Rota Expressa](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
O gráfico a seguir mostra um exemplo deste tipo de implantação. Para este exemplo, a Contoso é uma universidade localizada em Orlando, Flórida. A Contoso tem 10.000 membros e alunos da faculdade. Os testes de Internet de seu local com os sites de borda da Microsoft mostraram uma perda de pacote superior a 5% durante as horas pico de aula. Eles decidiram adquirir uma conexão dedicada para o Office usando a Rota Expressa com largura de banda provisionada a maior, assim eles podem evitar o congestionamento de rede para o Office 365 especialmente para o tráfego em tempo real do Skype for Business Online. Eles conectam-se à nuvem da Microsoft por meio da Rota Expressa no site MeetMe GA em Atlanta.
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### Somente implantação online - Vários sites no mesmo continente

Se sua empresa está usando os serviços do Skype for Business Online em vários escritórios na mesma região ou continente, e você optou por implementar a Rota Expressa do Azure, é recomendável conectar seu site principal por meio da Rota Expressa e, opcionalmente, adicionar um emparelhamento extra da Rota Expressa para outros locais que não atendam às metas de desempenho de rede recomendadas.
  
No exemplo a seguir, a Contoso é uma empresa de serviços de viagem dos EUA com sede em New York, mas com escritórios espalhados pelos Estados Unidos. Os escritórios são interconectados por meio de uma WAN que usa MPLS para se conectar com o Office 365. Inicialmente eles configuraram uma conexão de Rota Expressa usando seu roteador de Internet em Hoboken, New Jersey para o site MeetMe em New York. 
  
Com essa configuração, o tráfego de rede da maioria de seus sites com o Microsoft Network (site de borda em New York) pode atender às metas de desempenho de rede de conexão do cliente Skype for Business descritas em [Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge). No entanto, a latência entre os escritórios da costa oeste da Contoso com New York ultrapassa 50ms unidirecional. Além disso, Honolulu é o segundo maior escritório da Contoso, a latência de Honolulu para New York excede 80ms unidirecional. Para assegurar uma boa qualidade de mídias para os usuários nesses escritórios, a Contoso decidiu adicionar uma conexão de Rota Expressa da costa oeste entre o site de San Jose e o site MeetMe da Rota Expressa do Vale do Silício.
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### Somente implantação online - Vários sites em diferentes continentes

Se todos os seus usuários estiverem usando o serviço do Skype for Business Online, e se seus escritórios estiverem em vários locais físicos em vários continentes, se você decidir implantar a Rota Expressa do Azure, deverá configurar pelo menos uma conexão da Rota Expressa para cada continente entre cada site principal do continente para seu [local mais próximo de emparelhamento da Rota Expressa](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Dependendo do custo e do benefício, você pode escolher implantar conexões adicionais da Rota Expressa em sites onde as metas de desempenho de rede não são atendidas.
  
No exemplo a seguir, a Contoso é uma grande firma de advocacia corporativa com escritórios em grandes cidades espalhadas pela América do Norte e Europa. Com base em sua conexão de Internet e na avaliação do desempenho da rede interna, a Contoso decidiu implantar duas conexões de Rota Expressa na América do Norte e um único circuito de Rota Expressa para todos os seus escritórios europeus.
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### Problemas de configuração de implantação híbrida

Se você tem uma implantação do Lync ou Skype for Business nas instalações e opta por implementar uma integração híbrida do Skype for Business Online, recomendamos que se você decidir implantar a Rota Expressa do Azure, deverá ter pelo menos uma conexão de Rota Expressa para cada site de borda do Lync ou do Skype for Business das instalações e pelo menos uma conexão de Rota Expressa para cada continente com escritórios. Dependendo do custo e do benefício, para cada continente, você pode implantar conexões adicionais de Rota Expressa para escritórios onde as metas de desempenho de rede não estão sendo atendidas.
  
Se você tem uma implantação do Skype for Business nas instalações, deverá seguir o [Guia de Implantação e Planejamento de Servidor de Borda](https://technet.microsoft.com/en-us/library/mt346417.aspx). Os servidores de borda devem ser acessíveis, especificamente, de fora de sua rede. Isso geralmente é obtido pela atribuição de um endereço de IP público roteável ao servidor de borda ou uso da NAT (conversão de endereço de rede).
  
No exemplo a seguir, a Contoso tem uma implantação do Skype for Business Enterprise Voice nas instalações. Eles querem migrar os usuários das instalações para os serviços online do Office 365. Eles também decidiram usar uma implantação híbrida, assim poderão continuar usando a infraestrutura PSTN existente para todos os usuários nas instalações e online. O data center nas instalações da Contoso e os servidores de borda do Skype for Business estão em Chicago. Para sua implantação, a Contoso decidiu configurar uma conexão de Rota Expressa entre o data center de Chicago e a Rota Expressa de Chicago. Eles também adicionaram uma conexão de Rota Expressa da costa oeste para atender melhor ao escritório de Honolulu.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Implantação online com o Cloud Connector Edition

O Skype for Business Online Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de VMs (máquinas virtuais) empacotadas que implementam a conectividade PSTN nas instalações. Ao implantar uma topologia mínima do Skype for Business Server em um ambiente virtualizado, você poderá enviar e receber chamadas com telefones fixos e móveis por meio de infraestruturas de voz PSTN existentes nas instalações.
  
Se você decidir implantar a Rota Expressa do Azure e o Cloud Connector Edition, recomendamos que você configure pelo menos uma conexão de Rota Expressa para cada continente entre cada site principal do continente com seu [local mais próximo de emparelhamento da Rota Expressa](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Dependendo do custo e do benefício, você pode escolher implantar, em cada continente, as conexões adicionais da Rota Expressa de sites onde as metas de desempenho da rede não estão sendo atendidas.
  
Se você tiver uma implantação do Skype for Business nas instalações, deverá seguir o [Guia de Planejamento para o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Especificamente, devem ser atribuídos aos serviços do Access Edge e A/V Edge endereços de IP públicos e acessíveis dos data centers do Office 365.
  
No exemplo a seguir, a Contoso é uma firma de contabilidade europeia com presença em alguns dos principais países e cidades europeias. Quando assinaram o Skype for Business Online para todas as necessidades de colaboração, decidiram colocar um Cloud Connector para cada país/região onde tinham um local físico para continuar a usar sua infraestrutura PSTN e os contratos de operadoras existentes. Com base no teste de todos os seus sites e na borda de rede da Microsoft, determinaram que uma única conexão de Rota Expressa em Londres ajudaria a atender as metas de desempenho de rede do cliente Skype for Business descritas em [Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A seguir é apresentada outra opção de implantação para a Contoso. Neste caso, eles decidiram configurar uma conexão da Rota Expressa em cada site onde um Conector de Nuvem está implantado.
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## Consulte Também
<a name="bk_NetworkPerf"> </a>

#### 

[ExpressRoute e QoS no Skype for Business Online](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

