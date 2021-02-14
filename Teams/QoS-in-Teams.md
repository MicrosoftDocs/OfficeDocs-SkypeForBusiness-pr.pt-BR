---
title: Implementar Qualidade de Serviço no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba mais sobre como preparar a rede de QoS (Qualidade de Serviço) da sua organização no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766574"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar qoS (qualidade de serviço) no Microsoft Teams

A QoS (Qualidade de Serviço) no Microsoft Teams permite que o tráfego de rede em tempo real sensível a atrasos de rede (por exemplo, fluxos de voz ou vídeo) seja "cortado em linha" na frente do tráfego menos sensível (como baixar um novo aplicativo, em que um segundo extra para baixar não é um grande negócio). A QoS usa Objetos de Política de Grupo do Windows e Listas de Controle de Acesso baseadas em Porta para identificar e marcar todos os pacotes em fluxos em tempo real. Isso ajuda sua rede a dar fluxos de compartilhamento de voz, vídeo e tela a uma parte dedicada da largura de banda de rede.

Se você tem suporte para um grande grupo de usuários que estão enfrentando qualquer um dos problemas descritos neste artigo, provavelmente precisará implementar a QoS. Uma pequena empresa com poucos usuários pode não precisar de QoS, mas mesmo assim ela deve ser útil.

Sem alguma forma de QoS, você pode ver os seguintes problemas de qualidade na voz e no vídeo:

- Jitter – pacotes de mídia que chegam a taxas diferentes, o que pode resultar em palavras ou sílabas ausentes em chamadas
- Perda de pacote – pacotes descartados, o que também pode resultar em menos qualidade de voz e difícil de entender a fala
- Tempo de ida e volta atrasado (RTT) – pacotes de mídia que demoram muito para chegar aos destinos, o que resulta em atrasos perceptíveis entre duas partes em uma conversa e faz com que as pessoas se conversem entre si

A maneira menos complexa de resolver esses problemas é aumentar o tamanho das conexões de dados, internamente e na Internet. Como isso geralmente é proibitivo para custos, a QoS fornece uma maneira de gerenciar com mais eficiência os recursos que você tem em vez de adicionar largura de banda. Para resolver problemas de qualidade, recomendamos que você primeiro use qoS e, em seguida, adicione largura de banda somente quando necessário.

Para que a QoS seja eficaz, você deve aplicar configurações de QoS consistentes em toda a organização. Qualquer parte do caminho que não der suporte às suas prioridades de QoS pode prejudicar a qualidade das chamadas, vídeo e compartilhamento de tela. Isso inclui a aplicação de configurações a todos os PCs ou dispositivos do usuário, switches de rede, roteadores à Internet e ao serviço do Teams.

_Figura 1. A relação entre as redes de uma organização e os serviços do Microsoft 365 ou do Office 365_

![Ilustração da relação entre redes e serviços](media/Qos-in-Teams-Image1.png "A relação entre as redes de uma organização e os serviços do Microsoft 365 ou do Office 365: a rede local e os dispositivos se conectam a uma rede de conexão, que, por sua vez, se conecta ao Microsoft 365 ou aos serviços de Cloud Voice e AudioConferência do Office 365.")

## <a name="qos-implementation-checklist"></a>Lista de verificação de implementação de QoS

Em um nível alto, faça o seguinte para implementar a QoS:

1. [Certifique-se de que sua rede esteja pronta](#make-sure-your-network-is-ready)

1. [Selecionar um método de implementação de QoS](#select-a-qos-implementation-method)

1. [Escolher intervalos de porta iniciais para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type)

1. Implementar configurações de QoS:
   1. Em clientes que usam um GPO (Objeto de Política de Grupo) para [definir intervalos](QoS-in-Teams-clients.md) e marcações de porta do dispositivo cliente
   2. Em roteadores (consulte a documentação do fabricante) ou em outros dispositivos de rede. Isso pode incluir listas de controle de acesso baseadas em porta (ACLs) ou simplesmente definir as filas QoS e as marcações DSCP, ou todas elas.

      > [!IMPORTANT]
      > Recomendamos implementar essas políticas de QoS usando as portas de origem do cliente e um endereço IP de origem e destino de "qualquer". Isso capturará o tráfego de mídia de entrada e saída na rede interna.  

   3. [Definir como você deseja lidar com o tráfego de mídia para reuniões do Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide sua implementação de QoS](#validate-your-qos-implementation) analisando o tráfego do Teams na rede.

Conforme você se prepara para implementar a QoS, lembre-se das seguintes diretrizes:

- O caminho mais curto para o Microsoft 365 é o melhor
- Fechar portas só levará à degradação de qualidade
- Quaisquer obstáculos entre eles, como proxies, não são recomendados
- Limite o número de saltos:
  - Cliente para borda de rede – 3 a 5 saltos
  - ISP para a borda de rede da Microsoft – 3 saltos
  - Borda de rede da Microsoft para o destino final – irrelevante

Para obter informações sobre como configurar portas de firewall, vá para [URLs e intervalos IP do Office 365.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Certifique-se de que sua rede esteja pronta

Se você estiver considerando uma implementação de QoS, já deve ter determinado seus requisitos de largura de banda e outros [requisitos de rede.](prepare-network.md)
  
O congestionamento de tráfego em uma rede afetará muito a qualidade da mídia. A falta de largura de banda causa degradação de desempenho e uma experiência ruim do usuário. À medida que a adoção e o uso do Teams [crescem,](use-call-analytics-to-troubleshoot-poor-call-quality.md)use relatórios, análise de chamada por usuário e Painel de Qualidade de Chamada [(CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas e fazer ajustes usando QoS e adições seletivas de largura de banda.

### <a name="vpn-considerations"></a>Considerações sobre VPN

O QoS só funciona como esperado quando implementado em todos os links entre chamadores. Se você usar qoS em uma rede interna e um usuário entrar de um local remoto, você só poderá priorizar dentro de sua rede interna gerenciada. Embora locais remotos possam receber uma conexão gerenciada implementando uma VPN (rede virtual privada), uma VPN adiciona inerentemente sobrecarga de pacotes e cria atrasos no tráfego em tempo real. Recomendamos que você evite executar tráfego de comunicações em tempo real por meio de uma VPN.

Em uma organização global com links gerenciados que abrangem continentes, é recomendável qoS, pois a largura de banda para esses links é limitada em comparação com a LAN.

## <a name="introduction-to-qos-queues"></a>Introdução às filas de QoS

Para fornecer QoS, os dispositivos de rede devem ter uma maneira de classificar o tráfego e devem ser capazes de distinguir voz ou vídeo de outro tráfego de rede.

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se uma política de QoS não estiver configurada, haverá apenas uma fila e todos os dados serão tratados como de primeira, primeiro com a mesma prioridade. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode ficar preso atrás do tráfego, onde um atraso de alguns milissegundos extras não seria um problema.

Ao implementar a QoS, você define várias filas usando um dos vários recursos de gerenciamento de congestionamento, como a enfilagem de prioridade da Cisco e o [CBWFQ (Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) e os recursos de evitar congestionamento, como detecção antecipada aleatória [ponderada (WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Exemplos de filas de QoS_

![Ilustração de filas de QoS e divisão de largura de banda](media/Qos-in-Teams-Image2.png "A largura de banda total disponível é dividida entre várias filas ( áudio, vídeo e outros tráfegos) que foram atribuídas prioridades diferentes.")

Uma simples analógica é que a QoS cria "vias de carona" virtuais em sua rede de dados para que alguns tipos de dados nunca ou raramente se deparem com um atraso. Depois de criar essas raia, você pode ajustar seu tamanho relativo e gerenciar com muito mais eficiência a largura de banda de conexão que você tem, além de oferecer experiências de nível empresarial para os usuários da sua organização.

## <a name="select-a-qos-implementation-method"></a>Selecionar um método de implementação de QoS

Você pode implementar a QoS por meio de marcação baseada em porta, usando listas de controle do Access (ACLs) nos roteadores da sua rede. A marcação baseada em porta é o método mais confiável porque funciona em ambientes mistos do Windows, Mac e Linux e é a mais fácil de implementar. Os clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP, portanto, eles exigirão esse método.  

Usando a marcação baseada em porta, o roteador da sua rede examina um pacote de entrada e, se o pacote chegou usando uma determinada porta ou intervalo de portas, ele o identifica como um determinado tipo de mídia e o coloca na fila desse tipo, adicionando uma marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada ao header de Pacote IP para que outros dispositivos possam reconhecer seu tipo de tráfego e dar prioridade a ele na fila.

Embora a marcação baseada em porta funcione em plataformas, ela só marca o tráfego na borda WAN (não todo o caminho para o computador cliente) e cria sobrecarga de gerenciamento. Consulte a documentação fornecida pelo fabricante do roteador para obter instruções sobre como implementar este método.

### <a name="insert-dscp-markers"></a>Inserir marcadores DSCP

Você também pode implementar a QoS usando um OBJETO de Política de Grupo (GPO) para direcionar dispositivos cliente para inserir um marcador DSCP nos títulos de pacote IP identificando-o como um tipo específico de tráfego (por exemplo, voz). Roteadores e outros dispositivos de rede podem ser configurados para reconhecer isso e colocar o tráfego em uma fila separada e de prioridade mais alta.

Embora esse cenário seja totalmente válido, ele só funcionará para clientes do Windows que ingressaram no domínio. Qualquer dispositivo que não seja um cliente windows de domínio ingressado não será habilitado para marcação DSCP. Clientes como Mac OS têm marcas codificadas e sempre marcam o tráfego.

No lado positivo, controlar a marcação DSCP via GPO garante que todos os computadores que ingressaram no domínio recebam as mesmas configurações e que somente um administrador possa gerenciá-los. Os clientes que podem usar GPO serão marcados no dispositivo de origem e, em seguida, os dispositivos de rede configurados poderão reconhecer o fluxo em tempo real pelo código DSCP e dar a ele uma prioridade apropriada.

### <a name="best-practice"></a>Práticas práticas práticas

Recomendamos uma combinação de marcações DSCP no ponto de extremidade e acLs baseadas em porta em roteadores, se possível. Usar um GPO para capturar a maioria dos clientes e também usar a marcação DSCP baseada em porta garantirá que dispositivos móveis, Mac e outros clientes ainda recebam o tratamento QoS (pelo menos parcialmente).

As marcações DSCP podem ser curtidas aos carimbos de postagem que indicam aos trabalhadores postais como é urgente a entrega e como é melhor classificar para entregas rápidas. Depois de configurar sua rede para dar prioridade a fluxos de mídia em tempo real, os pacotes perdidos e os pacotes atrasados diminuirão muito.

Depois que todos os dispositivos na rede estão usando as mesmas classificações, marcações e prioridades, é possível reduzir ou eliminar atrasos, pacotes descartados e tremulações alterando o tamanho dos intervalos de porta atribuídos às filas usadas para cada tipo de tráfego. Na perspectiva do Teams, a etapa de configuração mais importante é a classificação e a marcação de pacotes. No entanto, para que a QoS de ponta a ponta seja bem-sucedida, você também precisa alinhar cuidadosamente a configuração do aplicativo com a configuração de rede subjacente. Depois que a QoS é totalmente implementada, o gerenciamento contínuo é uma questão de ajustar os intervalos de porta atribuídos a cada tipo de tráfego com base nas necessidades e no uso real da sua organização.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Escolher intervalos de porta iniciais para cada tipo de mídia

O valor DSCP informa a uma rede configurada correspondente qual prioridade dar a um pacote ou fluxo, se a marca DSCP é atribuída por clientes ou pela própria rede com base nas configurações de ACL. Cada carga de trabalho de mídia obtém seu próprio valor DSCP exclusivo (outros serviços podem permitir que cargas de trabalho compartilhem uma marcação DSCP, o Teams não o faz) e um intervalo de porta definido e separado usado para cada tipo de mídia. Outros ambientes podem ter uma estratégia de QoS existente, que ajudará você a determinar a prioridade das cargas de trabalho de rede.

O tamanho relativo dos intervalos de porta para cargas de trabalho de streaming em tempo real diferentes define a proporção da largura de banda total disponível dedicada a essa carga de trabalho. Para retornar à nossa analógica postal anterior: uma carta com o carimbo "Correio Aéreo" pode ser levado dentro de uma hora para o aeroporto mais próximo, enquanto um pequeno pacote marcado como "Email em Massa" pode esperar por um dia antes de viajar por terra em uma série de carros.

_Intervalos de portas iniciais recomendados_

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Esteja ciente do seguinte ao usar estas configurações:

- Se você planeja implementar o ExpressRoute no futuro e ainda não implementou a QoS, recomendamos seguir as orientações para que os valores DSCP sejam os mesmos de remetente para destinatário.
- Todos os clientes, incluindo clientes móveis e dispositivos Teams, usarão esses intervalos de porta e serão afetados por qualquer política DSCP que você implementar que use esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (clientes que permitem aos participantes ingressar em reuniões usando seus navegadores).
- Embora o cliente Mac use os mesmos intervalos de portas, ele também usa valores codificados para áudio (EF) e vídeo (AF41). Esses valores não são configuráveis.
- Se mais tarde você precisar ajustar os intervalos de portas para melhorar a experiência do usuário, os intervalos de portas não podem se sobrepor e devem ser adjacentes uns aos outros.

## <a name="migrate-qos-to-teams"></a>Migrar QoS para o Teams

Se você já implantou o Skype for Business Online, incluindo intervalos de porta e marcação de QoS, e agora está implantando. O Teams respeitará a configuração existente e usará os mesmos intervalos de porta e marcação que o cliente Skype for Business. Na maioria dos casos, nenhuma configuração adicional será necessária.

> [!NOTE]
> Se você estiver usando a marcação QoS do Nome do Aplicativo via Política de Grupo, deverá adicioná-Teams.exe como o nome do aplicativo.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS no Teams no Windows usando o PowerShell

**Definir QoS para áudio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Definir QoS para vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Definir QoS para compartilhamento**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gerenciando portas de origem no Centro de administração do Teams

No Teams, as portas de origem de QoS usadas pelas diferentes cargas de trabalho devem ser gerenciadas ativamente e ajustadas conforme necessário. Fazendo referência à tabela em Escolher [intervalos](#choose-initial-port-ranges-for-each-media-type)de porta iniciais para cada tipo de mídia, os intervalos de porta são ajustáveis, mas as marcações DSCP não são configuráveis. Depois de implementar essas configurações, você poderá descobrir que mais ou menos portas são necessárias para um determinado tipo de mídia. [A análise de](use-call-analytics-to-troubleshoot-poor-call-quality.md) chamada por usuário e o [CQD (Painel](turning-on-and-using-call-quality-dashboard.md) de Qualidade da Chamada) devem ser usados para tomar uma decisão para ajustar intervalos de porta após a implementação do Teams e periodicamente conforme as necessidades mudam.

> [!NOTE]
> Se você já configurou a QoS com base em intervalos de porta de origem e marcações DSCP para o Skype for Business Online, a mesma configuração será aplicada ao Teams e nenhuma alteração de cliente ou rede no mapeamento será necessária, embora talvez seja necessário definir os [intervalos](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) usados no Teams para corresponder ao que foi configurado para o Skype for Business Online.

Se você já implantou o Skype for Business Server no local, talvez seja necessário examinar suas políticas de QoS. Ajustar as políticas para corresponder às configurações de intervalo de porta que você verificou fornecem uma experiência de usuário de qualidade para o Teams.

## <a name="validate-your-qos-implementation"></a>Validar sua implementação de QoS

Para que a QoS seja eficaz, o valor DSCP definido pelo GPO precisa estar presente em ambas as extremidades de uma chamada. Ao analisar o tráfego gerado pelo cliente teams, você pode verificar se o valor DSCP não foi alterado ou removido quando o tráfego de carga de trabalho do Teams se move pela rede.

De preferência, você captura o tráfego no ponto de saída da rede. Você pode usar o espelhamento de porta em um switch ou roteador para ajudar com isso.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para outros dispositivos

Leia estes tópicos para obter informações sobre como implementar o QoS para Intune, Surface, iOS, Android e Mac

- [QoS para Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS para iOS, Android e Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Tópicos relacionados

- [Vídeo: Planejamento de rede](https://aka.ms/teams-networking)

- [Preparar a rede da organização para o Microsoft Teams](prepare-network.md)

- [Implementar QoS no cliente do Teams](QoS-in-Teams-clients.md)
