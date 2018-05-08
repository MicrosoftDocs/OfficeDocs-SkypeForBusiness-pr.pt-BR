---
title: Planejamento do controle de admissão de chamadas no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Saiba mais sobre o controle de admissão de chamada, que pode evitar chamadas de ocorrendo se eles teriam qualidade de mídia ruim, Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 11a73cb6065802b700694d6c3ffd589d935659db
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server-2015"></a>Planejamento do controle de admissão de chamadas no Skype for Business Server 2015
 
Saiba mais sobre o controle de admissão de chamada, que pode evitar chamadas de ocorrendo se eles teriam qualidade de mídia ruim, Skype para Business Server Enterprise Voice.
  
Para aplicativos baseados em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível das redes empresariais geralmente não é considerada um fator limitante nos ambientes de LAN. Entretanto, nos links WAN que interconectam locais, a largura de banda de rede pode ser limitada. 
  
Quando o tráfego de rede sobrecarrega um link WAN, mecanismos atuais, como enfileiramento, armazenamento em buffer e remoção de pacotes são usados para resolver o congestionamento. O tráfego extra é normalmente atrasado até que o congestionamento de rede melhore ou, se necessário, o tráfego seja removido. No caso de tráfego de dados convencional nessas situações, o cliente receptor pode se recuperar. Entretanto, para o tráfego em tempo real, como comunicações unificadas, o congestionamento da rede não pode ser resolvido dessa maneira, uma vez que o tráfego das comunicações unificadas é sensível à latência e à perda de pacotes. O congestionamento na WAN pode resultar em uma QoE (Qualidade da Experiência) ruim para os usuários finais. Para o tráfego em tempo real em condições congestionadas, é melhor negar as chamadas do que permitir conexões com qualidade ruim.
  
O CAC (controle de admissão de chamadas) determina se há largura de banda suficiente para estabelecer uma sessão em tempo real de qualidade aceitável. No Skype para Business Server, o CAC controla o tráfego somente de áudio e vídeo em tempo real, mas ela não afeta o tráfego de dados. Se o caminho de WAN padrão não tiver a largura de banda necessária, o CAC tentará encaminhar a chamada por um caminho de Internet ou pela PSTN (Rede Telefônica Pública Comutada). 
  
Esta seção descreve a funcionalidade de controle de admissão de chamada e explica como planejar o CAC.
  
> [!NOTE]
> Skype para Business Server tem três recursos avançados do Enterprise Voice: chamadas (CAC) do controle de admissão, serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral do planejamento de informações que são comuns a todos os três desses recursos, consulte [configurações de rede para os recursos avançados do Enterprise Voice no Skype para Business Server 2015](network-settings-for-advanced-features.md). 
  
O design CAC em Skype para Business Server oferece quatro principais atributos:
  
- É simples de implantar e gerenciar, sem a necessidade de equipamentos adicionais, como roteadores especialmente configurados.
    
- Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. As políticas CAC são aplicadas de acordo com a localização do ponto de extremidade, não onde o usuário está hospedado.
    
- Além de chamadas de voz, ele pode ser aplicado a outro tráfego, como chamadas de vídeo e sessões de conferência de áudio/vídeo.
    
- Oferece a flexibilidade para permitir a representação de vários tipos de topologias de rede. 
    
Se uma nova sessão de voz ou de vídeo exceder os limites de largura de banda definidos em um link WAN, a sessão será bloqueada ou (somente para telefonemas) reencaminhada para a PSTN.
  
O CAC controla o tráfego em tempo real somente para voz e vídeo. Ele não controla o tráfego de dados.
  
Os administradores definem as políticas CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de Front-End. Configurações de CAC automaticamente sejam propagadas para Skype todos para os servidores de Front End Business Server em sua rede.
  
Para chamadas que falham devido a políticas CAC, a ordem de precedência para o reencaminhamento da chamada é:
  
1. Internet
    
2. PSTN
    
3. Caixa postal
    
A gravação de detalhes da chamada (CDR) captura as informações sobre chamadas que são reencaminhadas para o PSTN ou o correio de voz. O CDR não captura as informações sobre chamadas reencaminhadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária. 
  
> [!NOTE]
> Os depósitos de caixa postal não serão negados devido a restrições da largura de banda. 
  
O Serviço de Política de Largura de Banda gera dois tipos de arquivos de log em formato de valores separados por vírgulas (CSV). O arquivo de log de **falhas de verificação** captura as informações quando as solicitações de largura de banda são negadas. O arquivo de log de **utilização de link** captura um instantâneo da topologia de rede e da utilização de largura de banda do link WAN. OS dois arquivos de log podem ajudá-lo a ajustar as políticas CAC com base na utilização.
  
## <a name="call-admission-control-considerations"></a>Considerações sobre o controle de admissão de chamadas

O administrador seleciona para instalar o Serviço de Política de Largura de Banda no primeiro pool configurado no local central. Como há um único local central por região da rede, há apenas um Serviço de Política de Largura de Banda por região da rede, que gerencia a política de largura de banda dessa região, os locais associados e os links para esses locais. O serviço de política de largura de banda é executado como parte dos servidores Front-End e, portanto, a alta disponibilidade é interna dentro desse pool. O serviço de política de largura de banda em execução em cada servidor Front-End sincroniza a cada 15 segundos. Se o pool de Front-End falhar, políticas CAC são impostas para esse site não são mais até o pool de Front-End e consequentemente o serviço de política de largura de banda estiver novamente operacional. Isso significa que todas as chamadas serão recebidas enquanto o Serviço de Política de Largura de Banda estiver fora de serviço. Portanto, é possível que ainda haja excesso de inscrição dos links na largura de banda durante esse período 
  
O serviço de política de largura de banda fornece alta disponibilidade em um pool de Front-End; No entanto, ele não fornece redundância em pools de Front-End. O serviço de política de largura de banda não é possível o failover de um pool de Front-End para outro. Depois que o serviço para o pool de Front-End é restaurado, o serviço de política de largura de banda é reiniciado e podem impor verificações de política de largura de banda novamente.
  
### <a name="network-considerations"></a>Considerações de rede

Embora a restrição de largura de banda de áudio e vídeo é imposta pelo serviço de política de largura de banda no Skype para Business Server, essa restrição não é imposta no roteador da rede (camada 2 e 3). O CAC não pode impedir que um aplicativo de dados, por exemplo, consuma a largura de banda de rede inteira em um link WAN, incluindo a largura de banda que está reservada para áudio e vídeo por sua política CAC. Para proteger a largura de banda necessária na rede, você pode implantar um protocolo QoS (Qualidade de Serviço), como os Serviços Diferenciados (DiffServ). Portanto, uma prática recomendada consiste em coordenar as políticas de largura de banda do CAC definidas com quaisquer configurações de QoS que você possa implantar.
  
### <a name="media-and-signaling-paths-over-vpn"></a>Caminhos de mídia e sinalização através de VPN

Se a sua empresa oferece suporte à mídia através de VPN, verifique se tanto o fluxo de mídia e o fluxo de sinalização vão através de VPN ou ambos são roteados pela internet. Por padrão, a mídia e os fluxos de sinalização passam pelo encapsulamento VPN.
  
### <a name="call-admission-control-of-outside-users"></a>Controle de admissão de chamadas de usuários externos

Controle não é imposta além dos limites do Skype para Business Server 2015 organização de admissão de chamada. CAC não pode ser aplicado ao tráfego de mídia atravessando a Internet, que não é gerenciada por Skype para Business Server 2015. Verificações CAC serão realizadas na parte da chamada que chegam através da rede corporativa, se o ponto de extremidade chamado pertence à organização e o servidor de borda foi adicionado à configuração de rede, conforme descrito em [controle de admissão de chamada implantação: lista de verificação final do Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/final-checklist.md). Se a extremidade chamada não pertencer à organização, como um usuário federado ou PIC, nenhuma verificação de política de largura de banda será realizada, e a chamada realizada ignorará quaisquer restrições do CAC.
  
### <a name="call-admission-control-of-pstn-connections"></a>Controle de Admissão de Chamada das Conexões PSTN

Controle de admissão de chamada é aplicável no servidor de mediação, independentemente se ele está conectado a um IP/PBX, um gateway PSTN ou um tronco SIP. Como o servidor de mediação é um agente de usuário em frente e verso (B2BUA), ele termina de mídia. Ele tem dois lados de conexão: um lado que esteja conectado a Skype para Business Server e um lado do gateway, que é conectado ao gateways PSTN, IP/PBXs ou troncos SIP. Para obter detalhes sobre conexões PSTN, consulte [Planejar a conectividade PSTN em Skype para Business Server 2015](pstn-connectivity-0.md).
  
CAC pode ser imposto em ambos os lados do servidor de mediação, a menos que o desvio de mídia está habilitado. Se o desvio de mídia está habilitado, o tráfego de mídia não atravessa o servidor de mediação, mas em vez disso fluirá diretamente entre o Skype para o cliente de negócios e o gateway. Nesse caso, o CAC não é necessário. Para obter detalhes, consulte [Plan for media bypass no Skype para negócios 2015](media-bypass.md).
  
A figura a seguir ilustra como o CAC é imposto a conexões PSTN, com e sem o bypass de mídia habilitado.
  
**Aplicação de controle de admissão de chamada em conexões para o PSTN**

![Imposição da conexão de bypass de mídia do CAC de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)
  
## <a name="defining-your-requirements-for-call-admission-control"></a>Definindo seus requisitos de controle de admissão de chamadas

O planejamento do CAC (controle de admissão de chamadas) requer informações detalhadas sobre a topologia da rede corporativa. Para ajudar a planejar suas políticas do serviço de controle de admissão de chamadas, execute as etapas a seguir.
  
1. Identifique os hubs/backbones (chamados de regiões de rede) dentro de sua rede corporativa.
    
2. Identifique os escritórios ou locais (chamados sites de rede) dentro de cada região de rede.
    
3. Determine a rota de rede entre cada par de regiões de rede.
    
4. Determine os limites de largura de banda para cada link WAN.
    
    > [!NOTE]
    > Limites de largura de banda consultem quanto da largura de banda em um link WAN que é alocado para o Enterprise Voice e o tráfego de áudio/vídeo. Quando um link WAN é descrito como "largura de banda restrita", o link de WAN tem um limite de largura de banda é menor que o tráfego de pico esperado por cima do link. 
  
5. Identifique as sub-redes IP atribuídas a cada local de rede.
    
Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.
  
**Exemplo de topologia para o controle de admissão de chamadas**

![Exemplo da topologia de rede do Litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)
  
> [!NOTE]
> Todos os locais de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nessa figura, são mostrados apenas links WAN que têm políticas de CAC aplicadas, com limites de largura de banda. Os locais de rede de Chicago, Nova York e Detroit são mostrados dentro da região oval da América do Norte, porque eles não estão com restrições largura de banda e não exigem políticas de CAC. 
  
Nesse exemplo, os componentes de topologia são explicados nas seções a seguir. Para obter detalhes sobre como essa topologia foi planejada, incluindo os limites de largura de banda, consulte [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server 2015](example-gathering-requirements.md).
  
### <a name="identify-network-regions"></a>Identificar as regiões de rede

Uma região de rede representa um backbone de rede ou um hub da rede.
  
Um backbone ou um hub de rede é uma parte da infraestrutura de rede do computador que interconecta diferentes partes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou sub-redes. Um backbone pode interligar diversas redes de um pequeno local para uma área geográfica ampla. A capacidade do backbone é normalmente maior do que as redes que se conectam a ele.
  
Nossa topologia de exemplo tem três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de locais de rede (consulte a definição de locais de rede posteriormente neste tópico). Trabalhe com sua equipe de operações de rede para identificar as regiões de rede.
  
### <a name="associating-a-central-site-with-each-network-region"></a>Associando um local central a cada região de rede

CAC exige que um Skype para o site central de Business Server é definido para cada região de rede. O local central é selecionado com a melhor conectividade de rede e maior largura de banda para todos os outros locais dessa região de rede. O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um local central que gerencia decisões do CAC. A partir do exemplo anterior, a associação apropriada será exibida na tabela a seguir.
  
> [!NOTE]
> Os locais centrais não correspondem necessariamente aos locais de rede. Nos exemplos desta documentação, alguns locais centrais (Chicago, Londres e Pequim) compartilham os mesmos nomes dos locais de rede. No entanto, mesmo se um site central e o site de rede compartilham o mesmo nome, o site central é um elemento do Skype para topologia de servidor de negócios, enquanto o site de rede é uma parte da rede geral no qual o Skype para a topologia Business Server reside. 
  
**Regiões de rede, sites centrais e sites de rede**

|**Região de rede**|**Site central**|**Sites de rede**|
|:-----|:-----|:-----|
|América do Norte  <br/> |Chicago  <br/> |Chicago  <br/> Nova York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Colônia  <br/> |
|APAC  <br/> |Pequim  <br/> |Pequim  <br/> Manila  <br/> |
   
### <a name="identify-network-sites"></a>Identificar os locais de rede

Um local de rede representa um local onde a sua organização tem um espaço físico, por exemplo, um escritórios, um conjunto de edifícios ou um campus. Um espaço físico com uma LAN e conectividade WAN para outros locais é considerado um local de rede. Iniciar o inventário de todos os escritórios da sua organização. Em nosso exemplo de topologia, a região de rede da América do Norte consiste nos seguintes locais de rede: Nova York, Chicago, Detroit, Portland, Reno e Albuquerque.
  
Você deve associar cada local de rede a uma região de rede. Dependendo se o local de rede tem um link WAN restrito, uma política de largura de banda será associada ao local de rede. Para obter detalhes sobre políticas de CAC e a largura de banda que você aloca ao usá-las, consulte "Definir as políticas de largura de banda" posteriormente neste tópico. Para configurar o CAC, associe os locais de rede às regiões de rede e, em seguida, crie políticas de alocação de largura de banda a serem aplicadas às conexões de largura de banda restrita entre um determinado local ou região e às conexões WAN entre os locais e as regiões. 
  
### <a name="identify-network-links"></a>Identificar os links de rede

Os links de rede as representam conexões WAN físicas que vinculam locais e regiões diferentes. Em nosso exemplo de topologia, há dois links de rede regionais, cinco links de rede entre locais e regiões e um link de rede entre dois locais.
  
Os dois links regionais estão entre América do Norte e EMEA, representado como NA-EMEA-LINK, e entre APAC e EMEA, representado como EMEA-APAC-LINK.
  
Os links de local são indicados por linhas que conectam Portland, Reno e Albuquerque à região da América do Norte, Manila à região APAC e Colônia à região EMEA. A linha entre Reno e Albuquerque mostra um link de rede direta entre esses dois locais.
  
### <a name="define-bandwidth-policies"></a>Definir as políticas de largura de banda

Trabalhe com sua equipe de operações de rede para determinar a quantidade de largura de banda WAN que está disponível para o tráfego de vídeo e áudio em tempo real entre os links WAN na organização. As políticas de largura de banda são geralmente aplicadas aos links WAN quando o uso de largura de banda é restrito, isso é, espera-se que ele seja maior do que a largura de banda que pode ser alocada para as modalidades de áudio e vídeo.
  
Políticas de largura de banda do CAC definem a largura de banda máxima que pode ser reservada para as modalidades de vídeo e de áudio em tempo real. Como o CAC não limita a largura de banda de outro tráfego, ele não pode impedir que outro tráfego de dados, como transferência de um arquivo grande, um streaming de música, use toda a largura de banda de rede.
  
As políticas de largura de banda do CAC podem definir o seguinte:
  
- Largura de banda total máxima alocada para áudio.
    
- Largura de banda total máxima alocada para vídeo.
    
- Largura de banda máxima alocada para uma única chamada de áudio (sessão).
    
- Largura de banda máxima alocada para uma única chamada de vídeo (sessão).
    
> [!NOTE]
> Todos os valores de largura de banda do CAC representam os limites de largura de banda máxima *unidirecional* .
  
> [!NOTE]
> O Skype para recursos de diretiva de voz do Business Server oferecem a capacidade de substituir a política de largura de banda verifica as chamadas de entrada para o usuário (não para chamadas de saída feitas pelo usuário). Depois que a sessão for estabelecida, o consumo da largura de banda será contabilizado com precisão. Essa configuração deve ser usada com moderação. Para obter detalhes, consulte [criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) ou [modificar uma política de voz e configurar registros de uso do PSTN](http://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) na documentação de implantação.
  
Para otimizar a utilização da largura de banda com base por sessão, considere o tipo de codecs de áudio e vídeo que serão usados. Mais especificamente, evite alocar menos largura de banda insuficiente ara um codec que você espera usar com frequência. Por outro lado, se quiser impedir que a mídia use um codec que exija mais largura de banda, defina a largura de banda máxima por sessão menor o suficiente para desencorajar esse uso. Para o áudio, nem todos os codecs estão disponíveis para cada cenário. Por exemplo:
  
- Chamadas de áudio ponto a ponto entre Skype para pontos de extremidade de negócios usarão RTAudio (8kHz) ou RTAudio (16kHz) quando você fator na largura de banda e priorização de codecs.
    
- Chamadas de conferência entre Skype para pontos de extremidade de negócios e de A / o serviço de conferência V usará 722 ou Siren.
    
- Chamadas para a rede telefônica pública comutada (PSTN) para ou do Skype para pontos de extremidade de negócios usarão 711 ou RTAudio (8kHz).
    
Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.
  
**Utilização de largura de banda por codecs**

|**Codec**|**Requisito de largura de banda com nenhuma correção de erro antecipada (FEC)**|**Requisito de largura de banda com correção de erro antecipada (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16 kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G. 711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G. 722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |NA (Not applicable)  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |NA (Not applicable)  <br/> |
   
> [!NOTE]
> Os requisitos de largura de banda consideram a sobrecarga de conta para o seguinte: Ethernet II, IP, UDP, RTP e SRTP. Eles também incluem 10 kbps para a sobrecarga RTCP. 
  
Os codecs G.722.1 e Siren são semelhantes, mas oferecem diferentes taxas de bits.
  
G. 722, o codec padrão para Skype para conferências Business Server, é completamente diferente dos 722.1 e Siren.
  
O codec Siren é usado Skype para Business Server nas seguintes situações:
  
- Quando a política de largura de banda está definida para que o G.722 seja usado.
    
- Se um cliente do Communications Server 2007 ou do Communications Server 2007 R2 se conecta a um Skype para o serviço de conferência Business Server (porque os clientes não suportam o codec g. 722).
    
**Utilização de largura de banda por cenário**

|**Cenário**|**Requisito de largura de banda otimizado por quantidade (kbps)**|**Requisito de largura de banda para modo balanceado (kbps)**|**Requisito de largura de banda otimizado por qualidade (kbps)**|
|:-----|:-----|:-----|:-----|
|Chamadas de áudio ponto a ponto  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Chamadas em conferência  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Chamadas PSTN (entre Skype para negócios e o gateway PSTN, com ignorar mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN entre (Skype for Business) e o servidor de mediação, sem ignorar mídia  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN (entre o servidor de mediação e gateway PSTN, sem ignorar mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chama do Skype para empresas - Polycom  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |
   
### <a name="identify-ip-subnets"></a>Identificar as sub-redes IP

Para cada local de rede, você precisará trabalhar com seu administrador de rede para determinar quais sub-redes IP são atribuídas para cada local de rede. Se seu administrador de rede já organizou as sub-redes IP em regiões de rede e locais de rede, seu trabalho é significantemente simplificado.
  
Em nosso exemplo, o local Nova York na região da América do Norte é atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Vamos supor que Bob, que geralmente trabalha em Detroit, viaje para o escritório de Nova York para treinamento. Quando ele ligar o computador e se conectar à rede, o computador obterá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.
  
> [!CAUTION]
> As sub-redes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato fornecido pelos computadores cliente para poderem ser usadas adequadamente para bypass de mídia. Um Skype para o cliente de negócios leva seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado a cada cliente, o Registrador Avançado comparará a lista de sub-redes IP associadas a cada local de rede na sub-rede fornecida pelo cliente para uma correspondência exata. Por esse motivo, é importante que as sub-redes inseridas durante a configuração de rede no servidor sejam sub-redes reais, e não virtuais. (Se implantar o controle de admissão de chamada, mas o bypass de mídia não, o controle de admissão de chamada funcionará corretamente, mesmo se você configurar o virtuais sub-redes.) Por exemplo, se um cliente entra em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede do IP de 255.255.255.0, Skype para negócios solicitará o ID de desvio associado à sub-rede 172.29.81.0. Se a sub-rede for definida como 172.29.0.0/16, embora o cliente pertença à sub-rede virtual, o Registrador Avançado não considerará isso uma correspondência porque ele está procurando especificamente pela sub-rede 172.29.81.0. Portanto, é importante que o administrador insere sub-redes exatamente como fornecidos pela Skype para clientes corporativos (que são provisionados com sub-redes durante a configuração de rede estática ou pelo DHCP.) 
  
## <a name="best-practices-for-call-admission-control"></a>Práticas recomendadas para controle de admissão de chamada

Para aprimorar o desempenho e facilitar a implantação, aplique as práticas recomendadas a seguir quando implantar o controle de admissão de chamadas:
  
- Garanta que as WANs estejam adequadamente provisionadas para o tráfego de mídia atual e antecipado.
    
    > [!NOTE]
    > É recomendável que você leve em consideração um buffer para seus limites de largura de banda. Existem cenários como condições de corrida que afetam a largura de banda total usada e podem resultar em situações em que o limite da largura de banda é excedido. Por exemplo, se duas chamadas tentarem iniciar enquanto o tráfego de mídia está alcançando um limite da largura de banda, uma delas pode ser recusada porque a outra conseguiu iniciar primeiro. 
  
- Monitore o uso da rede e os registros de detalhes de chamadas para que você possa escolher configurações de CAC ideais e atualizá-las conforme o uso da rede muda.
    
- Use políticas de largura de banda de CAC para complementar as configurações de QoS.
    
- Se você quiser reencaminhar chamadas bloqueadas na PSTN, verifique a funcionalidade e a capacidade da PSTN. Para obter detalhes, consulte [Planejamento saída roteamento de chamadas.](http://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx)
    
    > [!NOTE]
    > A capacidade refere-se ao número de portas que precisam ser abertas para oferecer suporte a um possível reencaminhamento da PSTN. 
  

