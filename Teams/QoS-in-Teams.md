---
title: Implementar Qualidade de Serviço no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba mais sobre como preparar a rede da sua organização para qoS (qualidade de serviço) no Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564139"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar qoS (qualidade de serviço) no Microsoft Teams

A QoS (Qualidade de Serviço) no Microsoft Teams permite que o tráfego de rede em tempo real que seja sensível a atrasos de rede (por exemplo, fluxos de voz ou vídeo) seja "cortado na linha" na frente do tráfego menos sensível (como baixar um novo aplicativo, em que um segundo extra para baixar não é grande coisa). A QoS usa objetos Política de Grupo Windows e listas de Controle de Acesso baseadas em porta para identificar e marcar todos os pacotes em fluxos em tempo real. Isso ajuda sua rede a fornecer aos fluxos de voz, vídeo e compartilhamento de tela uma parte dedicada da largura de banda da rede.

Se você dá suporte a um grande grupo de usuários que estão enfrentando qualquer um dos problemas descritos neste artigo, provavelmente precisará implementar a QoS. Uma pequena empresa com poucos usuários pode não precisar de QoS, mas mesmo lá ela deve ser útil.

Sem alguma forma de QoS, você pode ver os seguintes problemas de qualidade em voz e vídeo:

- Tremulação – pacotes de mídia que chegam a taxas diferentes, o que pode resultar em palavras ou sílabas ausentes em chamadas
- Perda de pacotes – pacotes descartados, o que também pode resultar em menor qualidade de voz e fala difícil de entender
- RTT (tempo de ida e volta) atrasado – pacotes de mídia que demoram muito para alcançar seus destinos, o que resulta em atrasos perceptíveis entre duas partes em uma conversa e faz com que as pessoas conversem entre si

A maneira menos complexa de resolver esses problemas é aumentar o tamanho das conexões de dados, tanto internamente quanto na Internet. Como isso geralmente é proibitivo de custo, a QoS fornece uma maneira de gerenciar com mais eficiência os recursos que você tem em vez de adicionar largura de banda. Para resolver problemas de qualidade, recomendamos que você primeiro use a QoS e, em seguida, adicione largura de banda somente quando necessário.

Para que a QoS seja eficaz, você deve aplicar configurações de QoS consistentes em toda a organização. Qualquer parte do caminho que não dá suporte às suas prioridades de QoS pode prejudicar a qualidade das chamadas, vídeo e compartilhamento de tela. Isso inclui a aplicação de configurações a todos os computadores ou dispositivos de usuário, comutadores de rede, roteadores para a Internet e o serviço do Teams.

_Figura 1. A relação entre as redes de uma organização e o Microsoft 365 ou Office 365 serviços_

![Ilustração da relação entre redes e serviços.](media/Qos-in-Teams-Image1.png "A relação entre as redes de uma organização e os serviços do Microsoft 365 ou Office 365: a rede local e os dispositivos se conectam a uma rede de interconexão, que, por sua vez, se conecta aos serviços de Audioconferência e Voz da Nuvem do Microsoft 365 ou Office 365.")

## <a name="qos-implementation-checklist"></a>Lista de verificação de implementação de QoS

Em um alto nível, faça o seguinte para implementar a QoS:

1. [Verifique se a rede está pronta](#make-sure-your-network-is-ready).

1. [Selecione um método de implementação de QoS](#select-a-qos-implementation-method).

1. [Escolha intervalos de portas iniciais para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type).

1. Implemente as configurações de QoS:
   1. Em clientes que usam um GPO (objeto Política de Grupo) para [definir marcações e intervalos](QoS-in-Teams-clients.md) de portas do dispositivo cliente.
   2. Em roteadores (consulte a documentação do fabricante) ou em outros dispositivos de rede. Isso pode incluir ACLs (listas de Controle de Acesso baseadas em porta) ou simplesmente definir as filas de QoS e marcações DSCP ou todas elas.

      > [!IMPORTANT]
      > É recomendável implementar essas políticas de QoS usando as portas de origem do cliente e um endereço IP de origem e destino de "qualquer". Isso capturará o tráfego de mídia de entrada e saída na rede interna.  

   3. [Defina como você deseja lidar com o tráfego de mídia para reuniões do Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. [Valide sua implementação de QoS](#validate-your-qos-implementation) analisando o tráfego do Teams na rede.

Ao se preparar para implementar a QoS, lembre-se das seguintes diretrizes:

- O caminho mais curto para o Microsoft 365 é o melhor.
- Fechar portas só levará à degradação da qualidade.
- Quaisquer obstáculos entre eles, como proxies, não são recomendados.
- Limite o número de saltos:
  - Cliente para borda de rede – 3 a 5 saltos
  - ISP para borda de rede da Microsoft – 3 saltos
  - Borda de rede da Microsoft para o destino final – irrelevante

Para obter informações sobre como configurar portas de firewall, [acesse Office 365 URLs e intervalos de IP](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Verifique se a rede está pronta

Se você estiver considerando uma implementação de QoS, já deverá ter determinado seus requisitos de largura de banda e outros [requisitos de rede](prepare-network.md).
  
O congestionamento de tráfego em uma rede afetará muito a qualidade da mídia. A falta de largura de banda leva à degradação do desempenho e a uma experiência de usuário ruim. À medida que a adoção e o uso do Teams [aumentam, use](use-call-analytics-to-troubleshoot-poor-call-quality.md) relatórios, análise de chamadas por usuário e [CQD (](turning-on-and-using-call-quality-dashboard.md) Painel de Qualidade de Chamada) para identificar problemas e, em seguida, fazer ajustes usando QoS e adições seletivas de largura de banda.

### <a name="vpn-considerations"></a>Considerações sobre VPN

A QoS só funciona conforme o esperado quando implementada em todos os links entre chamadores. Se você usar a QoS em uma rede interna e um usuário entrar de um local remoto, só poderá priorizar dentro de sua rede interna e gerenciada. Embora os locais remotos possam receber uma conexão gerenciada implementando uma VPN (rede virtual privada), uma VPN adiciona inerentemente a sobrecarga de pacotes e cria atrasos no tráfego em tempo real. Recomendamos que você evite executar o tráfego de comunicações em tempo real por meio de uma VPN.

Em uma organização global com links gerenciados que abrangem continentes, é altamente recomendável a QoS porque a largura de banda para esses links é limitada em comparação com a LAN.

## <a name="introduction-to-qos-queues"></a>Introdução às filas de QoS

Para fornecer QoS, os dispositivos de rede devem ter uma maneira de classificar o tráfego e devem ser capazes de distinguir voz ou vídeo de outro tráfego de rede.

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se uma política de QoS não estiver configurada, haverá apenas uma fila e todos os dados serão tratados como primeiro a entrar, primeiro a sair com a mesma prioridade. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode ficar preso atrás do tráfego em que um atraso de alguns milissegundos extras não seria um problema.

Ao implementar a QoS, você define várias filas usando um dos vários recursos de gerenciamento de congestionamento, como o enfileiramento prioritário da Cisco e o [CBWFQ (](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) Enfileiramento Justo Ponderado Baseado em Classe) e recursos de prevenção de congestionamento, como [WRED (](https://en.wikipedia.org/wiki/Weighted_random_early_detection)detecção antecipada aleatória ponderada).

_Figura 2. Exemplos de filas de QoS_

![Ilustração de filas de QoS e divisão de largura de banda.](media/Qos-in-Teams-Image2.png "A largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que foram atribuídas a prioridades diferentes.")

Uma analogia simples é que a QoS cria "pistas de carona" virtuais em sua rede de dados para que alguns tipos de dados nunca ou raramente encontre um atraso. Depois de criar essas pistas, você poderá ajustar seu tamanho relativo e gerenciar com muito mais eficiência a largura de banda de conexão que tem, enquanto ainda fornece experiências de nível empresarial para os usuários da sua organização.

## <a name="select-a-qos-implementation-method"></a>Selecionar um método de implementação de QoS

Você pode implementar a QoS por meio de marcação baseada em porta, usando ACLs (listas de Controle de Acesso) em roteadores da rede. A marcação baseada em porta é o método mais confiável porque funciona em ambientes mistos do Windows, Mac e Linux e é a mais fácil de implementar. Os clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP, portanto, eles exigirão esse método.  

Usando a marcação baseada em porta, o roteador da rede examina um pacote de entrada e, se o pacote chegou usando uma determinada porta ou intervalo de portas, ele o identifica como um determinado tipo de mídia e o coloca na fila para esse tipo, adicionando uma marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada ao cabeçalho pacote IP para que outros dispositivos possam reconhecer seu tipo de tráfego e dar prioridade a ele em sua fila.

Embora a marcação baseada em porta funcione entre plataformas, ela marca apenas o tráfego na borda wan (não todo o caminho para o computador cliente) e cria sobrecarga de gerenciamento. Consulte a documentação fornecida pelo fabricante do roteador para obter instruções sobre como implementar esse método.

### <a name="insert-dscp-markers"></a>Inserir marcadores DSCP

Você também pode implementar a QoS usando um GPO (objeto Política de Grupo) para direcionar os dispositivos cliente a inserir um marcador DSCP em cabeçalhos de pacotes IP identificando-o como um tipo específico de tráfego (por exemplo, voz). Roteadores e outros dispositivos de rede podem ser configurados para reconhecer isso e colocar o tráfego em uma fila separada e de prioridade mais alta.

Embora esse cenário seja totalmente válido, ele só funcionará para clientes windows ingressados no domínio. Qualquer dispositivo que não seja um cliente Windows ingressado no domínio não será habilitado para marcação DSCP. Outros clientes, como aqueles que executam o macOS, têm marcas codificadas e sempre marcarão o tráfego.

No lado positivo, controlar a marcação DSCP por meio do GPO garante que todos os computadores ingressados no domínio recebam as mesmas configurações e que apenas um administrador possa gerenciá-los. Os clientes que podem usar GPO serão marcados no dispositivo de origem e, em seguida, os dispositivos de rede configurados poderão reconhecer o fluxo em tempo real pelo código DSCP e dar a ele uma prioridade apropriada.

### <a name="best-practice"></a>Prática recomendada

Recomendamos uma combinação de marcações DSCP no ponto de extremidade e ACLs baseadas em porta em roteadores, se possível. Usar um GPO para capturar a maioria dos clientes e também usar a marcação DSCP baseada em porta garantirá que dispositivos móveis, Mac e outros clientes ainda recebam tratamento de QoS (pelo menos parcialmente).

As marcações DSCP podem ser associadas a carimbos de postagem que indicam aos trabalhadores postais quão urgente é a entrega e como melhor classifique-a para entrega rápida. Depois de configurar sua rede para dar prioridade a fluxos de mídia em tempo real, os pacotes perdidos e os pacotes atrasados devem diminuir muito.

Depois que todos os dispositivos na rede estão usando as mesmas classificações, marcações e prioridades, é possível reduzir ou eliminar atrasos, pacotes descartados e tremulação alterando o tamanho dos intervalos de porta atribuídos às filas usadas para cada tipo de tráfego. Da perspectiva do Teams, a etapa de configuração mais importante é a classificação e a marcação de pacotes. No entanto, para que a QoS de ponta a ponta seja bem-sucedida, você também precisa alinhar cuidadosamente a configuração do aplicativo com a configuração de rede subjacente. Depois que a QoS é totalmente implementada, o gerenciamento contínuo é uma questão de ajustar os intervalos de porta atribuídos a cada tipo de tráfego com base nas necessidades e no uso real da sua organização.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Escolher intervalos de portas iniciais para cada tipo de mídia

O valor DSCP informa a uma rede configurada correspondentemente qual prioridade fornecer a um pacote ou fluxo, se a marca DSCP é atribuída por clientes ou pela própria rede com base nas configurações de ACL. Cada carga de trabalho de mídia obtém seu próprio valor DSCP exclusivo (outros serviços podem permitir que as cargas de trabalho compartilhem uma marcação DSCP, o Teams não faz) e um intervalo de portas definido e separado usado para cada tipo de mídia. Outros ambientes podem ter uma estratégia de QoS existente em vigor, o que ajudará você a determinar a prioridade das cargas de trabalho de rede.

O tamanho relativo dos intervalos de portas para diferentes cargas de trabalho de streaming em tempo real define a proporção da largura de banda total disponível dedicada a essa carga de trabalho. Para retornar à nossa analogia postal anterior: uma carta com um carimbo "Air Mail" pode ser levada dentro de uma hora para o aeroporto mais próximo, enquanto um pequeno pacote marcado como "Bulk Mail" marca pode esperar por um dia antes de viajar por terra em uma série de caminhões.

_Intervalos de portas iniciais recomendados_

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Lembre-se do seguinte ao usar estas configurações:

- Se você planeja implementar o ExpressRoute no futuro e ainda não implementou a QoS, recomendamos que você siga as diretrizes para que os valores DSCP sejam os mesmos do remetente para o destinatário.

- Todos os clientes, incluindo clientes móveis e dispositivos do Teams, usarão esses intervalos de portas e serão afetados por qualquer política DSCP que você implementar que use esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (clientes que permitem que os participantes ingressem em reuniões usando seus navegadores).

- Embora o cliente Mac use os mesmos intervalos de portas, ele também usa valores embutidos em código para áudio (EF) e vídeo (AF41). Esses valores não são configuráveis.

- Se você precisar ajustar posteriormente os intervalos de portas para melhorar a experiência do usuário, os intervalos de porta não poderão se sobrepor e devem ser adjacentes uns aos outros.

## <a name="migrate-qos-to-teams"></a>Migrar QoS para o Teams

Se você já implantou o Skype for Business Online, incluindo marcação de QoS e intervalos de portas, e agora está implantando. O Teams respeitará a configuração existente e usará os mesmos intervalos de porta e marcação que o Skype for Business cliente. Na maioria dos casos, nenhuma configuração adicional será necessária.

> [!NOTE]
> Se você estiver usando a marcação QoS do Nome do Aplicativo Política de Grupo, deverá adicioná-Teams.exe como o nome do aplicativo.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS no Teams no Windows usando o PowerShell

**Definir QoS para áudio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Definir QoS para vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Definir QoS para compartilhamento**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gerenciando portas de origem no centro de administração do Teams

No Teams, as portas de origem de QoS usadas pelas diferentes cargas de trabalho devem ser gerenciadas ativamente e ajustadas conforme necessário. Referindo-se à tabela em Escolher [intervalos](#choose-initial-port-ranges-for-each-media-type) de portas iniciais para cada tipo de mídia, os intervalos de portas são ajustáveis, mas as marcações DSCP não são configuráveis. Depois de implementar essas configurações, você poderá descobrir que mais ou menos portas são necessárias para um determinado tipo de mídia. [A análise de chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) por usuário e o [CQD (](turning-on-and-using-call-quality-dashboard.md) Painel de Qualidade de Chamada) devem ser usados para tomar uma decisão para ajustar os intervalos de portas após a implementação do Teams e periodicamente conforme as necessidades mudam.

> [!NOTE]
> Se você já tiver configurado a QoS com base em intervalos de porta de origem e marcações DSCP para o Skype for Business Online, a mesma configuração será aplicada ao Teams e nenhuma alteração adicional de cliente ou rede no mapeamento será necessária, embora você precise definir os [intervalos](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) usados no Teams para corresponder ao que foi configurado para o Skype for Business Online.

Se você já implantou Skype for Business Server local, talvez seja necessário examinar novamente suas políticas de QoS. Ajuste as políticas para corresponder às configurações de intervalo de portas verificadas, fornecendo uma experiência de usuário de qualidade para o Teams.

## <a name="validate-your-qos-implementation"></a>Validar sua implementação de QoS

Para que a QoS seja eficaz, o valor DSCP definido pelo GPO precisa estar presente em ambas as extremidades de uma chamada. Analisando o tráfego gerado pelo cliente do Teams, você pode verificar se o valor DSCP não foi alterado ou removido quando o tráfego de carga de trabalho do Teams se move pela rede.

Preferencialmente, você captura o tráfego no ponto de saída de rede. Você pode usar o espelhamento de porta em um comutador ou roteador para ajudar com isso.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para outros dispositivos

Leia estes tópicos para obter informações sobre como implementar qoS para Intune, Surface, iOS, Android e Mac

- [QoS para Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](/surface-hub/surface-hub-qos)

- [QoS para iOS, Android e Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Tópicos relacionados

- [Vídeo: Planejamento de rede](https://aka.ms/teams-networking)

- [Preparar a rede da organização para o Microsoft Teams](prepare-network.md)

- [Implementar QoS no cliente do Teams](QoS-in-Teams-clients.md)