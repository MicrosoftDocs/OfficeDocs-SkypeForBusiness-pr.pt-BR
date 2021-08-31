---
title: Implementar Qualidade de Serviço no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como preparar a rede da sua organização para qoS (Qualidade de Serviço) em Microsoft Teams.
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
ms.openlocfilehash: f87dfea2eb847a8bf6ae4c6aa95b099d93b0c1e0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732930"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar a QoS (Qualidade de Serviço) no Microsoft Teams

A qualidade do serviço (QoS) no Microsoft Teams permite o tráfego de rede em tempo real que é sensível a atrasos de rede (por exemplo, fluxos de voz ou vídeo) para "cortar na linha" em frente ao tráfego menos sensível (como baixar um novo aplicativo, onde um segundo a mais para baixar não é uma grande transação). O QoS usa Windows de Política de Grupo e Listas de Controle de Acesso baseados em Porta para identificar e marcar todos os pacotes em fluxos em tempo real. Isso ajuda sua rede a dar aos fluxos de voz, vídeo e compartilhamento de tela uma parte dedicada da largura de banda da rede.

Se você suportar um grande grupo de usuários que estão enfrentando qualquer um dos problemas descritos neste artigo, provavelmente precisará implementar a QoS. Uma pequena empresa com poucos usuários pode não precisar de QoS, mas mesmo lá ela deve ser útil.

Sem alguma forma de QoS, você pode ver os seguintes problemas de qualidade em voz e vídeo:

- Tremência – pacotes de mídia que chegam a taxas diferentes, o que pode resultar em palavras ou sílabas ausentes em chamadas
- Perda de pacotes – pacotes descartados, o que também pode resultar em menor qualidade de voz e difícil de entender a fala
- Tempo de ida e volta atrasado (RTT) – pacotes de mídia que demoram muito tempo para alcançar seus destinos, o que resulta em atrasos perceptíveis entre duas partes em uma conversa e faz com que as pessoas conversem entre si

A maneira menos complexa de resolver esses problemas é aumentar o tamanho das conexões de dados, internamente e na Internet. Como isso geralmente é proibitivo de custos, o QoS fornece uma maneira de gerenciar com mais eficiência os recursos que você tem em vez de adicionar largura de banda. Para resolver problemas de qualidade, recomendamos que você primeiro use QoS e adicione largura de banda somente quando necessário.

Para que a QoS seja eficaz, você deve aplicar configurações de QoS consistentes em toda a sua organização. Qualquer parte do caminho que não dá suporte às suas prioridades de QoS pode degradar a qualidade de chamadas, vídeo e compartilhamento de tela. Isso inclui a aplicação de configurações a todos os PCs ou dispositivos do usuário, comutadores de rede, roteadores para a Internet e o serviço Teams usuário.

_Figura 1. A relação entre as redes de uma organização e os serviços Microsoft 365 ou Office 365 de uma organização_

![Ilustração da relação entre redes e serviços.](media/Qos-in-Teams-Image1.png "A relação entre as redes de uma organização e os serviços Microsoft 365 ou Office 365: rede local e dispositivos se conectam a uma rede de interconexão, que, por sua vez, se conecta aos serviços Microsoft 365 ou Office 365 Cloud Voice e Audioconferência.")

## <a name="qos-implementation-checklist"></a>Lista de verificação de implementação de QoS

Em um nível alto, faça o seguinte para implementar qoS:

1. [Certifique-se de que sua rede esteja pronta](#make-sure-your-network-is-ready).

1. [Selecione um método de implementação QoS](#select-a-qos-implementation-method).

1. [Escolha intervalos de porta iniciais para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type).

1. Implementar configurações de QoS:
   1. Em clientes que usam um OBJETO de Política de Grupo (GPO) para [definir intervalos](QoS-in-Teams-clients.md)e marcações de porta de dispositivo cliente.
   2. Em roteadores (consulte a documentação do fabricante) ou em outros dispositivos de rede. Isso pode incluir listas de controle de acesso baseadas em porta (ACLs) ou simplesmente definir as filas de QoS e as marcações DSCP, ou todas elas.

      > [!IMPORTANT]
      > Recomendamos implementar essas políticas de QoS usando as portas de origem do cliente e um endereço IP de origem e destino de "qualquer". Isso capturará o tráfego de mídia de entrada e saída na rede interna.  

   3. [De definir como você deseja lidar com o tráfego de mídia para Teams reuniões.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide sua implementação de QoS](#validate-your-qos-implementation) analisando Teams tráfego na rede.

Ao se preparar para implementar a QoS, tenha em mente as seguintes diretrizes:

- O caminho mais curto para Microsoft 365 é o melhor.
- As portas de fechamento só levarão à degradação da qualidade.
- Quaisquer obstáculos entre eles, como proxies, não são recomendados.
- Limite o número de saltos:
  - Cliente para borda de rede – 3 a 5 saltos
  - ISP para Borda de rede da Microsoft – 3 saltos
  - Borda de rede da Microsoft para destino final – irrelevante

Para obter informações sobre como configurar portas de firewall, acesse [Office 365 URLs e intervalos DE IP.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Certifique-se de que sua rede esteja pronta

Se você estiver considerando uma implementação de QoS, já deve ter determinado seus requisitos de largura de banda e outros requisitos [de rede.](prepare-network.md)
  
O congestionamento de tráfego em uma rede afetará muito a qualidade da mídia. A falta de largura de banda leva à degradação do desempenho e a uma experiência de usuário ruim. À medida que Teams adoção e uso aumenta, use [relatórios,](use-call-analytics-to-troubleshoot-poor-call-quality.md)análise de chamada por usuário e Painel de Qualidade de Chamada [(CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas e, em seguida, fazer ajustes usando QoS e adições seletivas de largura de banda.

### <a name="vpn-considerations"></a>Considerações sobre VPN

O QoS só funciona conforme o esperado quando implementado em todos os links entre chamadores. Se você usar QoS em uma rede interna e um usuário entrar de um local remoto, você só poderá priorizar dentro de sua rede interna gerenciada. Embora locais remotos possam receber uma conexão gerenciada implementando uma VPN (rede virtual privada), uma VPN adiciona inerentemente a sobrecarga de pacotes e cria atrasos no tráfego em tempo real. Recomendamos que você evite executar o tráfego de comunicações em tempo real em uma VPN.

Em uma organização global com links gerenciados que abrangem continentes, recomendamos a QoS porque a largura de banda para esses links é limitada em comparação com a LAN.

## <a name="introduction-to-qos-queues"></a>Introdução às filas de QoS

Para fornecer QoS, os dispositivos de rede devem ter uma maneira de classificar o tráfego e devem ser capazes de distinguir voz ou vídeo de outro tráfego de rede.

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se uma política de QoS não estiver configurada, haverá apenas uma fila e todos os dados serão tratados como de primeira, primeiro com a mesma prioridade. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode ficar preso atrás do tráfego, onde um atraso de alguns milissegundos extras não seria um problema.

Ao implementar a QoS, você define várias filas usando um dos vários recursos de gerenciamento de congestionamento, como a fila de prioridade da Cisco e a Fila Justa Ponderada Com Base em Classe [(CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) e recursos de evitação de congestionamento, como a detecção aleatória antecipada [ponderada (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Figura 2. Exemplos de filas QoS_

![Ilustração das filas de QoS e divisão de largura de banda.](media/Qos-in-Teams-Image2.png "A largura de banda total disponível é dividida entre várias filas, áudio, vídeo e outros tráfegos, que foram atribuídas a prioridades diferentes.")

Uma analogia simples é que o QoS cria "faixas de carpool" virtuais em sua rede de dados para que alguns tipos de dados nunca ou raramente encontram um atraso. Depois de criar essas faixas, você pode ajustar seu tamanho relativo e gerenciar muito mais efetivamente a largura de banda de conexão que você tem, enquanto ainda fornece experiências de nível comercial para os usuários da sua organização.

## <a name="select-a-qos-implementation-method"></a>Selecione um método de implementação QoS

Você pode implementar a QoS por meio de marcação baseada em porta, usando Listas de Controle de Acesso (ACLs) nos roteadores da sua rede. A marcação baseada em porta é o método mais confiável porque funciona em ambientes Windows, Mac e Linux mistos e é o mais fácil de implementar. Os clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP, portanto, eles exigirão esse método.  

Usando a marcação baseada em porta, o roteador da rede examina um pacote de entrada e, se o pacote chegou usando uma determinada porta ou intervalo de portas, ele o identifica como um determinado tipo de mídia e o coloca na fila desse tipo, adicionando uma marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada ao header do Pacote IP para que outros dispositivos possam reconhecer seu tipo de tráfego e dar prioridade à fila.

Embora a marcação baseada em porta funcione entre plataformas, ela marca apenas o tráfego na borda WAN (não até a máquina cliente) e cria sobrecarga de gerenciamento. Consulte a documentação fornecida pelo fabricante do roteador para obter instruções sobre a implementação desse método.

### <a name="insert-dscp-markers"></a>Inserir marcadores DSCP

Você também pode implementar a QoS usando um GPO (Objeto de Política de Grupo) para direcionar dispositivos cliente para inserir um marcador DSCP em headers de pacotes IP identificando-o como um tipo específico de tráfego (por exemplo, voz). Roteadores e outros dispositivos de rede podem ser configurados para reconhecer isso e colocar o tráfego em uma fila separada e de prioridade mais alta.

Embora esse cenário seja totalmente válido, ele funcionará apenas para clientes Windows de domínio. Qualquer dispositivo que não seja um cliente Windows de domínio não estará habilitado para marcação DSCP. Outros clientes, como aqueles que executam macOS, têm marcas codificadas em código e sempre marcarão o tráfego.

No lado positivo, controlar a marcação DSCP via GPO garante que todos os computadores ingressados no domínio recebam as mesmas configurações e que apenas um administrador possa gerenciá-los. Os clientes que podem usar GPO serão marcados no dispositivo de origem e, em seguida, os dispositivos de rede configurados podem reconhecer o fluxo em tempo real pelo código DSCP e dar a ele uma prioridade apropriada.

### <a name="best-practice"></a>Prática prática prática

Recomendamos uma combinação de marcações DSCP no ponto de extremidade e ACLs baseadas em porta em roteadores, se possível. Usar um GPO para capturar a maioria dos clientes e também usar a marcação DSCP baseada em porta garantirá que o celular, Mac e outros clientes ainda recebam tratamento QoS (pelo menos parcialmente).

As marcações DSCP podem ser comparados a carimbos de postagem que indicam aos funcionários postais a urgência da entrega e a melhor maneira de classificar para entrega rápida. Depois de configurar sua rede para dar prioridade a fluxos de mídia em tempo real, os pacotes perdidos e os pacotes atrasados devem diminuir muito.

Depois que todos os dispositivos na rede estão usando as mesmas classificações, marcações e prioridades, é possível reduzir ou eliminar atrasos, pacotes descartados e tremidos alterando o tamanho dos intervalos de porta atribuídos às filas usadas para cada tipo de tráfego. Na perspectiva Teams, a etapa de configuração mais importante é a classificação e a marcação de pacotes. No entanto, para que a QoS de ponta a ponta seja bem-sucedida, você também precisa alinhar cuidadosamente a configuração do aplicativo com a configuração de rede subjacente. Depois que a QoS for totalmente implementada, o gerenciamento contínuo será uma questão de ajustar os intervalos de porta atribuídos a cada tipo de tráfego com base nas necessidades e no uso real da sua organização.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Escolha intervalos de porta iniciais para cada tipo de mídia

O valor DSCP informa a uma rede configurada correspondentemente qual prioridade dar a um pacote ou fluxo, se a marca DSCP é atribuída por clientes ou pela própria rede com base nas configurações de ACL. Cada carga de trabalho de mídia obtém seu próprio valor DSCP exclusivo (outros serviços podem permitir que cargas de trabalho compartilhem uma marcação DSCP, Teams não o faz) e um intervalo de porta definido e separado usado para cada tipo de mídia. Outros ambientes podem ter uma estratégia de QoS existente, o que ajudará você a determinar a prioridade das cargas de trabalho de rede.

O tamanho relativo dos intervalos de porta para cargas de trabalho de streaming em tempo real diferentes define a proporção do total de largura de banda disponível dedicada a essa carga de trabalho. Para retornar à nossa analogia postal anterior: uma carta com um carimbo "Air Mail" pode ser levada dentro de uma hora para o aeroporto mais próximo, enquanto um pequeno pacote marcado como "Correio em Massa" pode aguardar um dia antes de percorrer a terra em uma série de camiões.

_Intervalos de portas iniciais recomendados_

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Esteja ciente do seguinte ao usar estas configurações:

- Se você planeja implementar o ExpressRoute no futuro e ainda não implementou a QoS, recomendamos que você siga as diretrizes para que os valores DSCP sejam os mesmos de remetente para receptor.

- Todos os clientes, incluindo clientes móveis e dispositivos Teams, usarão esses intervalos de porta e serão afetados por qualquer política DSCP que você implementar que use esses intervalos de porta de origem. Os únicos clientes que continuarão usando portas dinâmicas são os clientes baseados em navegador (clientes que permitem que os participantes participem de reuniões usando seus navegadores).

- Embora o cliente Mac use os mesmos intervalos de porta, ele também usa valores codificados para áudio (EF) e vídeo (AF41). Esses valores não são configuráveis.

- Se você precisar ajustar posteriormente os intervalos de porta para melhorar a experiência do usuário, os intervalos de porta não poderão se sobrepor e devem ser adjacentes uns aos outros.

## <a name="migrate-qos-to-teams"></a>Migrar QoS para Teams

Se você tiver implantado o Skype for Business Online, incluindo marcação QoS e intervalos de porta, e agora estiver implantando. Teams, Teams respeitará a configuração existente e usará os mesmos intervalos de porta e marcação que o Skype for Business cliente. Na maioria dos casos, nenhuma configuração adicional será necessária.

> [!NOTE]
> Se você estiver usando a marcação QoS nome do aplicativo por meio da Política de Grupo, adicione Teams.exe como o nome do aplicativo.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS em Teams em Windows usando o PowerShell

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

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gerenciando portas de origem no Teams de administração

Em Teams, as portas de origem QoS usadas pelas diferentes cargas de trabalho devem ser gerenciadas ativamente e ajustadas conforme necessário. Referindo-se à tabela em [Escolher intervalos](#choose-initial-port-ranges-for-each-media-type)de porta iniciais para cada tipo de mídia , os intervalos de porta são ajustáveis, mas as marcações DSCP não são configuráveis. Depois de implementar essas configurações, você pode descobrir que mais ou menos portas são necessárias para um determinado tipo de mídia. [A análise de](use-call-analytics-to-troubleshoot-poor-call-quality.md) chamada por usuário e o Painel de Qualidade de Chamada [(CQD)](turning-on-and-using-call-quality-dashboard.md) devem ser usados na tomada de uma decisão para ajustar intervalos de porta após a implementação Teams e periodicamente conforme as necessidades de alteração.

> [!NOTE]
> Se você já configurou a QoS com base em intervalos de porta de origem e marcações DSCP para o Skype for Business Online, a mesma configuração se aplicará ao Teams e nenhuma outra alteração de cliente ou rede no mapeamento será necessária, embora seja necessário definir os [intervalos](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) usados no Teams para corresponder ao que foi configurado para o Skype for Business Online.

Se você tiver implantado o Skype for Business Server local, talvez seja necessário examinar suas políticas de QoS. Ajustar as políticas para corresponder às configurações de intervalo de porta verificadas fornecem uma experiência de usuário de qualidade para Teams.

## <a name="validate-your-qos-implementation"></a>Validar sua implementação de QoS

Para que a QoS seja efetiva, o valor DSCP definido pelo GPO precisa estar presente nas duas extremidades de uma chamada. Analisando o tráfego gerado pelo cliente Teams, você pode verificar se o valor DSCP não foi alterado ou removido quando o tráfego de carga de trabalho Teams se move pela rede.

Preferencialmente, você captura o tráfego no ponto de saída da rede. Você pode usar o espelhamento de porta em uma opção ou roteador para ajudar com isso.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para outros dispositivos

Leia estes tópicos para obter informações sobre a implementação de QoS para Intune, Surface, iOS, Android e Mac

- [QoS para Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](/surface-hub/surface-hub-qos)

- [QoS para iOS, Android e Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Tópicos relacionados

- [Vídeo: Planejamento de rede](https://aka.ms/teams-networking)

- [Preparar a rede da organização para o Microsoft Teams](prepare-network.md)

- [Implementar QoS no cliente Teams cliente](QoS-in-Teams-clients.md)