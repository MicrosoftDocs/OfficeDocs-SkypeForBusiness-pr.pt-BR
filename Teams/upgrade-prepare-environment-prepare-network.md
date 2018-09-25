---
title: Preparar sua rede para atualizar para o Teams - Microsoft Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use essas orientações para preparar sua rede para a implantação e a distribuição do Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6814fde066e1b9d1fc8d5e1a5d099c1f72c81ef6
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013711"
---
![Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")

Este artigo faz parte do estágio de prontidão técnica de sua atualização jornada, uma atividade que você concluir em paralelo com o estágio de preparação do usuário. Antes de continuar, confirme que você tiver concluído essas atividades desde estágios anteriores:

-   [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Preparar sua rede para atualizar para o Teams

Se você estiver implantando o áudio, vídeo ou reuniões, você pode realizar algumas etapas adicionais para otimizar a sua rede para essa funcionalidade. Equipes usa o áudio e vídeo tecnologia (codecs) que pode se adaptar a — e, portanto, têm um melhor desempenho em — mais condições de rede. Para garantir o desempenho ideal e consistente, você deve preparar sua rede para equipes.

![Diagrama que descreve os três componentes da qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco na rede.](media/evaluate-my-environment-image1.png "Diagrama que descreve os três componentes da qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco sobre a rede.")

## <a name="why-should-you-prepare-your-network"></a>Por que você precisa preparar sua rede?

Antes de observarmos as etapas a serem tomadas, é importante entender o que pode afetar o desempenho das equipes e, portanto, satisfação e felicidade do usuário. Três áreas principais de risco podem afetar como usuários percebem a qualidade da rede:

-   Largura de banda insuficiente disponível

-   Bloqueadores de firewall e proxy

-   Deficiências de rede, como jitter e perda de pacotes

As etapas descritas a seguir o ajudarão a determinar que se a sua implantação poderá ser afetada por qualquer um desses fatores e ajudará você progride uma resolução. Falhar preparar sua rede levarão provavelmente aos usuários insatisfeitos e corrige dispendiosa, da ad hoc. Por Otimize sua rede — e a sua organização — para equipes, você pode aumentar drasticamente sua chance de sucesso.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planejamento de largura de banda

A primeira etapa para a preparação da rede é garantir que sua rede tenha largura de banda suficiente disponível para as modalidades que equipes irá fornecer aos usuários. Planejamento da largura de banda suficiente é uma tarefa razoavelmente simples e iniciar uma barreira de muito baixa para ajudar a garantir a seus usuários terão uma experiência de equipes de alta qualidade.

Você iniciar o seu planejamento de jornada para equipes do [Supervisor de meu site](https://myadvisor.fasttrack.microsoft.com/) usando Planejador de rede de largura de banda. Planejador de rede fornece largura de banda de cada site de planejamento para equipes e oferece recomendações para otimizar o desempenho da rede.

> [!IMPORTANT]
> Se a largura de banda necessária não estiver disponível, a pilha de mídia dentro de equipes cai a qualidade da sessão de áudio/vídeo para acomodar essa menor quantidade de largura de banda disponível, o que afeta a qualidade da chamada ou reunião. O cliente de equipes tenta priorizar a qualidade do áudio sobre a qualidade do vídeo. Portanto, é extremamente importante ter esperada de largura de banda disponível.


|Atividade  |Largura de banda para download  |Largura de banda para upload  |Fluxo de tráfego |
|---------|---------|---------|---------|
|**Chamada de áudio ponto a ponto**     |0,1 Mbps         |0,1 Mbps        |Cliente <> Cliente         |
|**Chamada de áudio ponto a ponto (tela inteira)**     |4 Mbps         |4 Mbps         |Cliente <> Cliente          |
|**Compartilhamento de desktop ponto a ponto (resolução de 1920&#215;1080)**     |4 Mbps         |4 Mbps         |Cliente <> Cliente          |
|**Reunião de dois participantes**     |4 Mbps         |4 Mbps         |Cliente <> Office 365         |
|**Reunião de três participantes**     |8 Mbps         |6,5 Mbps         |Cliente <> Office 365           |
|**Reunião de quatro participantes**     |5,5 Mbps         |4 Mbps         |Cliente <> Office 365           |
|**Reunião de cinco ou mais participantes**     |6 Mbps         |1,5 Mbps         |Cliente <> Office 365           |

### <a name="local-internet-egress"></a>Saída para a Internet local

Muitas redes foram projetados para usar um hub e spoke de topologia. Nessa topologia, o tráfego da internet geralmente percorre WAN com um datacenter central antes de ele surge (egresses) para a internet. Normalmente, isso é feito para centralizar dispositivos de segurança de rede com o objetivo de reduzir o custo total.

Tráfego de back-puxar pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como Teams Microsoft opera em uma rede grande de global da Microsoft, geralmente há um local de rede aos e está perto do usuário. Um usuário provavelmente receberá um melhor desempenho por egressing sem um ponto de internet local e está perto do seu local e em nossa rede de voz-otimizado assim que possível. Para algumas cargas de trabalho, as solicitações de DNS são usadas para enviar o tráfego para o mais próximo do servidor front-end. Nesses casos, é importante que, ao usar um ponto de saída local, ele é emparelhado com resolução DNS local.

Otimizar o caminho de rede para a rede global da Microsoft, melhorar o desempenho e basicamente oferecer a melhor experiência para usuários. Para obter mais detalhes, consulte o blog postar [Obtendo o melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).


Para obter uma experiência ideal usando mídia em tempo real dentro Teams da Microsoft, você deverá atender os requisitos de rede para o Office 365. Para mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Os dois segmentos de rede a serem definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge) devem atender aos seguintes requisitos:


|**Valor**  |**Cliente para o Microsoft Edge**  |**Edge do cliente para o Microsoft Edge**  |
|---------|---------|---------|
|**Latência (unidirecional)**     |< 50 ms          |< 30 ms          |
|**Latência (tempo resposta ou RTT)** |< 100 ms         |< 60 ms         |
|**Perda de pacote de intermitência**    |<10% durante qualquer intervalo de 200 ms         |<1% durante qualquer intervalo de 200 ms         |
|**Perda de pacote**     |<1% durante qualquer intervalo de 15 s          |<0,1% durante qualquer intervalo de 15 s         |
|**Tremulação entre chegadas de pacote**    |<30 ms durante qualquer intervalo de 15 s         |<15 ms durante qualquer intervalo de 15 s         |
|**Reordenação de pacotes**    |<0,05% de pacotes com problemas         |<0,01% de pacotes com problemas         |

Para testar os dois segmentos de rede, use a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada diretamente no computador cliente e em um computador conectado ao Customer Network Edge. Essa ferramenta contém uma documentação limitada, mas uma documentação mais profunda do uso da ferramenta pode ser encontrada aqui: [Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=855800). Ao executar essa Avaliação da prontidão da rede, você pode validar a prontidão da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Essa é a mesma Avaliação da prontidão da rede recomendada para clientes que estão buscando implantar o Skype for Business.


### <a name="vpn"></a>VPN

VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, eles estão geralmente não projetados ou configurados para oferecer suporte a mídia em tempo real. Alguns VPNs também podem não suportar UDP. VPNs também introduzem uma camada adicional de criptografia, na parte superior de tráfego de mídia que já está criptografado. Além disso, a conectividade com o serviço de equipes talvez não seja eficiente devido ao tráfego de fixação de forma por meio de um dispositivo VPN. Além disso, eles não são necessariamente projetados de uma perspectiva de capacidade para acomodar as cargas antecipadas que precisarão de equipes.

A recomendação é fornecer um caminho alternativo que ignora a VPN para tráfego de equipes. Isso normalmente é conhecido como *divisão de túnel VPN*. Divida encapsulamento significa que o tráfego para o Office 365 não atravessa VPN, mas será levado diretamente para o Office 365. Essa alteração terá um impacto positivo na qualidade, mas também proporciona a vantagem secundária de reduzir a carga de dispositivos VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

### <a name="wi-fi"></a>Wi-Fi

Como o VPN, redes Wi-Fi não são necessariamente projetadas ou configuradas para oferecer suporte a mídia em tempo real. Planejando ou otimizando, uma rede Wi-Fi para equipes de suporte é uma consideração importante para uma implantação de alta qualidade.

Existem vários fatores que entram em cena para otimizar uma rede Wi-Fi:

-   Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

-   Posicionamento de ponto de planejamento e otimizando as faixas Wi-Fi e acesso. O intervalo de 2,4 GHz pode fornecer uma experiência adequada dependendo de posicionamento de ponto de acesso, mas os pontos de acesso geralmente são afetados por outros dispositivos de consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado à mídia em tempo real devido ao seu intervalo densidade, mas exige mais pontos de acesso para obter cobertura suficiente. Pontos de extremidade também precisam oferecer suporte a esse intervalo e ser configurado para aproveitar nessas faixas de acordo.

-   Se forem implantados redes Wi-Fi de banda dupla, considere a implementação de direcionamento de banda. _O direcionamento de banda_ é uma técnica implementada por fornecedores de Wi-Fi para influenciar a banda dupla aos clientes utilizarem o intervalo de 5 GHz.

-   Quando os pontos de acesso no mesmo canal estiverem muito juntos, eles podem causar sobreposição de sinal e competem acidentalmente, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso que estão próximas umas das outras estão em canais que não se sobreponham.

Fornecedor de cada sem fio tem seus próprio recomendações para a implantação de sua solução sem fio. Recomendamos que você consulte seu fornecedor para obter orientações específicas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de proxy e firewall

Microsoft Teams se conecta ao Microsoft Online Services e precisa de conectividade de internet para que isso. Para as equipes funcionar corretamente, você deve abrir as portas TCP 80 e 443 dos clientes com a internet e portas UDP 3478 por meio de 3481 dos clientes com a internet. As portas TCP são usadas para se conectar ao conteúdo baseado na web, como o SharePoint Online, o Exchange Online e os serviços de equipes de bate-papo. Plug-ins e conectores também se conectar por essas portas TCP. Quatro portas UDP são usadas para a mídia, como áudio e vídeo, para garantir que elas fluem corretamente.

Abertura dessas portas é essencial para uma implantação de equipes confiável. Bloquear essas portas não é suportado e afetará a qualidade da mídia.

Se sua organização requer que você especifique o exato intervalos de endereços IP e domínios ao qual essas portas devem ser abertas, você pode restringir os domínios para essas portas e intervalos IP de destino. Para obter uma lista de exatas portas, protocolos e intervalos IP, consulte [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Se você escolher restringir os intervalos de endereços IP de destino e os domínios, certifique-se de manter a lista de intervalos de porta e atualizado porque eles podem ser alteradas. Você pode assinar [este RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) para serem atualizadas quando ocorrem alterações. Também é uma boa prática para testar se todas as portas são abertas executando o [Skype para ferramenta de avaliação de rede comercial](https://www.microsoft.com/download/details.aspx?id=53885) regularmente. Você pode encontrar mais informações sobre a funcionalidade dessa ferramenta na próxima seção.

No caso de um servidor de proxy que está sendo implantado, recomendamos que você ignorar o servidor proxy para todos os serviços de equipes. Embora usando um proxy pode funcionar, é bem provável que qualidade será reduzida devido da mídia sendo forçados a usar TCP em vez de UDP. Para obter mais informações sobre os servidores proxy e ignorando, consulte [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Considerações de rede adicionais
### <a name="external-name-resolution"></a>Resolução do nome externo

Certifique-se de que todos os computadores cliente que executam o cliente Teams possam resolver consultas externas de DNS para descobrir os serviços fornecidos pelo Office 365.

### <a name="nat-pool-size"></a>Tamanho do pool de NAT

Quando vários usuários e dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.

Para atenuar esse risco, certifique-se de adequada endereços IP públicos são atribuídos para os pools NAT para evitar o esgotamento de porta. O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectarem aos serviços do Office 365. Para mais informações, consulte o [guia Suporte de NAT com o Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Detecção de intrusões e guia de prevenção

Se o seu ambiente tiver um sistema de detecção de intrusões e/ou sistema de prevenção de intrusões implantado para uma camada extra de segurança para conexões de saída, verifique se o tráfego que tem URLs do Office 365 como destino está na lista de permissões.

## <a name="test-the-network"></a>Testar a rede

Depois de concluir a preparação de planejamento e rede — incluindo a atualização de largura de banda e abrindo portas no firewall — você deve testar o desempenho da sua rede. Os resultados deste teste será pintar uma imagem mais nítida de qualquer otimização de rede ou remediação necessários para o sucesso da implementação equipes.

Você pode baixar o [Skype para ferramenta de avaliação de rede comercial](https://www.microsoft.com/download/details.aspx?id=53885) para testar se a sua rede está pronta para equipes. A ferramenta oferece a funcionalidade dual: ele pode testar se a todas as portas corretas foram abertas e, em seguida, ele pode testar para problemas de rede.

Depois que baixar e instala a ferramenta, você pode encontrá-lo em c:\\Program Files\\Microsoft Skype para ferramenta de avaliação de rede comercial. Uma orientação detalhada sobre como usar a ferramenta, Usage.docx, está incluída nesse diretório.

### <a name="test-for-opened-ports"></a>Testar portas abertas

Abra uma janela de prompt de comando e navegue até o diretório de rede Assessment Tool, inserindo **cd c:\\Program Files\\Microsoft Skype para ferramenta de avaliação de rede comercial**. No prompt de comando, inicie o teste de portas abertos inserindo o **networkassessmenttool.exe /connectivitycheck**

Depois de executar as verificações, a ferramenta irá exibir a mensagem "Verificações concluído com êxito" ou enviar relatórios sobre as portas que foram bloqueadas. Ele também gera um arquivo chamado Connectivity_results.txt, que contém a saída da ferramenta e armazena-o na pasta % userprofile %\\appdata\\local\\microsoft Skype para ferramenta de avaliação de rede comercial\\ directory.

Recomendamos a execução das verificações de conectividade regularmente para verificar se as portas foram abertas e estão funcionando corretamente.

### <a name="test-for-network-impairments"></a>Testar falhas de rede

Para aumentar a satisfação do usuário, você deve limitar quaisquer deficiências em sua rede. Os problemas de rede mais comuns são atraso (latência), perda de pacote e tremulação:

-   **Latência:** Esse é o tempo que leva para obter um pacote IP do ponto A ponto b na rede. Esse atraso de propagação de rede essencialmente está vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional tomada por vários roteadores entre si. Latência é medida como tempo unidirecional ou de ida e volta.

-   **Perda de pacotes**: isso geralmente é definido como uma porcentagem de pacotes que são perdidos em uma determinada janela de tempo. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos tendo quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.

-   **Tremulação de chegada de pacotes entre ou simplesmente tremulação:** Esta é a média alteração em atraso entre pacotes sucessivos. Mais moderno software de VoIP, incluindo Skype para os negócios, pode se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante perceberá os efeitos de variação.

Os valores máximos para esses problemas são descritos no [desempenho de conectividade de rede e qualidade de mídia](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Quando o teste esses problemas, podemos distinguir entre dois segmentos separados:

-   O *segmento de borda* é o segmento na qual reside o seu roteador. Esse é o segmento de rede lógica mais próximo conectado à internet em cada um dos seus locais. Na maioria dos casos, esse é o ponto de conexão do roteador ou, possivelmente, em uma rede de perímetro (também conhecida como *DMZ*, *zona desmilitarizada*e *sub-rede filtrada*). Nenhum tráfego adicional que afeta os dispositivos que não seja o roteador deve ocorrer entre esse segmento e a internet.

-   O *segmento do cliente* é o segmento de rede lógica em que seus clientes residem.

Você deve testar os dois segmentos usando a ferramenta de avaliação de rede. Para testar o segmento, navegue até o diretório e insira **networkassessmenttool.exe** no prompt de comando. Os resultados são gravados em um arquivo chamado Results.tsv e compará-los com os [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para cada segmento.

Observe que os dois segmentos devem cumprir os requisitos para uma implantação de alta qualidade. Recomendamos que você execute a ferramenta várias vezes por uma hora diretamente para fazer uma boa indicação de desempenho da sua rede.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correção de rede

Se os resultados do planejamento de largura de banda, testes de porta ou testes de requisitos de rede mostrarem que a rede atual precisa de correção antes de implantar o Teams, isso poderá ser feito de várias maneiras: 

-   Para largura de banda insuficiente, atualize as conexões para que o tráfego para o Office 365 possa fluir sem impedimentos.

-   Para portas bloqueadas, altere as regras de firewall e teste-as novamente.

-   Para falhas de rede, sempre execute uma análise da causa raiz.

Qualidade de serviço (QoS) pode ser usado para deficiências batalha priorização e separando o tráfego. Algumas organizações optam por implantar o QoS para superar os problemas de largura de banda ou restringir a quantidade de fluxo de tráfego. Isso não melhorar a qualidade e levarão à redução novos problemas. Uma análise de causa raiz deve ser sempre executada quando os problemas de rede excedem requisitos. QoS pode ser uma solução. Para obter mais informações, consulte [Qualidade de serviço em equipes da Microsoft](qos-in-teams.md).

>[!NOTE]
>Muitas redes evoluem ao longo do tempo devido às atualizações, expansão ou outros requisitos de negócios. Certifique-se de que você tenha processos operacionais in-loco para manter nessas áreas como parte do seu planejamento de gerenciamento de serviço.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Ponto de decisão</td><td><ul><li>Quem será o responsável por realizar as devidas avaliações de rede em todos os segmentos de rede e locais da organização?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Você pode executar uma avaliação de rede detalhado para ajudar a garantir que sua rede está pronta para sua implantação do Microsoft Teams. Para obter mais informações, consulte [Avaliação de prontidão de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Execute a correção de rede com base nos resultados da avaliação de prontidão de rede para cada segmento de rede.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Principais conclusões

Estes são os argumentos principais desta orientação. Faça o seguinte:

-   Abra as portas TCP 80 e 443 de saída dos clientes que usarão o Teams.

-   Abra portas UDP 3478 a 3481 de saída dos clientes que usarão o Teams.

-   Certifique-se de ter largura de banda suficiente para implantar o Teams, completando o [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Execute a [Ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) e certifique-se de atender aos requisitos descritos em [Qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) tanto para o segmento de borda, como para o segmento do cliente.
