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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 465112aa154620f4cabf59aa1e6d4c70aa74eb16
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887801"
---
![Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme se você concluiu essas atividades dos estágios anteriores:

-   [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Preparar sua rede para atualizar para o Teams

Se você está implantando áudio, vídeo ou reuniões, você pode realizar algumas etapas adicionais para otimizar sua rede para essa funcionalidade. O Teams usa tecnologia de áudio e vídeo (codecs) que podem se adaptar à maioria das condições de rede e, portanto, tem um melhor desempenho nelas. Para garantir um desempenho ideal e consistente, você deve preparar sua rede para o Teams.

![Diagrama que descreve os três componentes da qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco na rede.](media/evaluate-my-environment-image1.png "Diagrama que descreve os três componentes da qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco sobre a rede.")

## <a name="why-should-you-prepare-your-network"></a>Por que você precisa preparar sua rede?

Antes de analisarmos as etapas a serem seguidas, é importante entender o que pode afetar o desempenho do Teams e, assim, a felicidade e a satisfação dos usuários. Três principais áreas de risco podem afetar como os usuários percebem a qualidade de rede:

-   Largura de banda insuficiente disponível

-   Bloqueadores de firewall e proxy

-   Deficiências de rede, como jitter e perda de pacotes

As etapas descritas abaixo ajudarão você a verificar se sua implantação pode ser afetada por algum desses fatores e a progredir para uma solução. Provavelmente, se deixar de preparar sua rede, os usuários ficarão insatisfeitos e haverá correções ad-hoc dispendiosas. Ao preparar sua rede e sua organização para o Teams, você pode aumentar significativamente sua chance de sucesso.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planejamento de largura de banda

A primeira etapa da preparação da rede é garantir que a rede tenha largura de banda suficiente disponível para as modalidades que o Teams oferecerá aos usuários. O planejamento de largura de banda suficiente é uma tarefa bastante simples, com um início de poucas barreiras, para ajudar a garantir que seus usuários tenham uma experiência de alta qualidade no Teams.

Você pode começar sua jornada de planejamento de largura de banda para o Teams no [site My Advisor](https://myadvisor.fasttrack.microsoft.com/) usando o Planejador de rede. O Planejador de rede oferece planejamento de largura de banda por site para o Teams e recomendações para otimizar o desempenho da rede.

> [!IMPORTANT]
> Se a largura de banda necessária não estiver disponível, a pilha de mídia dentro do Teams prejudicará a qualidade da sessão de áudio/vídeo para acomodar a menor largura de banda disponível, afetando a qualidade da chamada ou reunião. O cliente do Teams tenta priorizar a qualidade do áudio em relação à qualidade do vídeo. Assim, é extremamente importante ter disponível a largura de banda esperada.


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

Muitas redes foram projetadas para usar uma topologia hub-spoke. Nessa topologia, normalmente o tráfego da Internet percorre a WAN até um data center central antes de exteriorizar-se (sair) na Internet. Muitas vezes, isso é feito para centralizar os dispositivos de segurança de rede a fim de reduzir o custo total.

O tráfego de retorno pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como o Microsoft Teams é executado na ampla rede global da Microsoft, frequentemente há um local de emparelhamento de rede perto do usuário. O usuário provavelmente terá melhor desempenho ao sair de um ponto de Internet local próximo de sua localização e entrar em nossa rede com otimização de voz assim que possível. Para algumas cargas de trabalho, solicitações DNS são usadas para enviar o tráfego para o servidor front-end mais próximo. Nesses casos, é importante que, ao usar um ponto de saída local, ele esteja emparelhado com a resolução de DNS local.

A otimização do caminho de rede para a rede global da Microsoft melhorará o desempenho e, em última instância, oferecerá a melhor experiência para os usuários. Para obter mais detalhes, consulte a postagem no blog [Como obter a melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).


Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, é necessário atender aos requisitos de rede do Office 365. Para obter mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

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

As VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, não costumam ser projetados ou configurados para ter suporte à mídia em tempo real. Algumas VPNs também podem não dar suporte ao UDP. As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado. Além disso, a conectividade com o serviço do Teams pode não ser eficiente devido ao tráfego excessivo por meio de um dispositivo VPN. Além disso, eles não são necessariamente projetados com a perspectiva de capacidade para acomodar as cargas previstas de que o Teams precisará.

A recomendação é fornecer um caminho alternativo que contorne a VPN para o tráfego do Microsoft Teams. Geralmente, isso é conhecido como *VPN de túnel dividido*. Túnel dividido significa que o tráfego do Office 365 não atravessará a VPN, mas irá diretamente para o Office 365. Essa alteração tem um impacto positivo sobre a qualidade, mas também apresenta um benefício secundário de reduzir a carga dos dispositivos de VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

### <a name="wi-fi"></a>Wi-Fi

Como a VPN, as redes Wi-Fi não são necessariamente projetadas ou configuradas para oferecer suporte à mídia em tempo real. Planejar ou otimizar uma rede Wi-Fi para oferecer suporte ao Teams é uma consideração importante para uma implantação de alta qualidade.

Existem vários fatores que entram em cena para otimizar uma rede Wi-Fi:

-   Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

-   Planejar e otimizar as bandas de Wi-Fi e a colocação do ponto de acesso. O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real porque é mais denso, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.

-   Se forem implantadas redes Wi-Fi de banda dupla, considere implementar a direção de banda. A _direção de banda_ é uma técnica implementada por fornecedores de Wi-Fi para influenciar os clientes de banda dupla a usar o intervalo de 5 GHz.

-   Quando pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e competir involuntariamente, resultando em uma experiência deficiente para o usuário. Certifique-se de que os pontos de acesso próximos um do outro estejam em canais que não se sobreponham.

Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Recomendamos que você consulte as orientações específicas do fornecedor.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de proxy e firewall

O Microsoft Teams se conecta ao Microsoft Online Services e, para isso, precisa de conectividade com a Internet. Para que o Teams funcione corretamente, é preciso abrir as portas TCP 80 e 443 dos clientes para a internet e as portas UDP 3478 a 3481 dos clientes para a internet. As portas TCP são usadas para conexão a conteúdo baseado na web, como o SharePoint Online, o Exchange Online e os serviços de bate-papo do Teams. Plugins e conectores também se conectam por essas portas TCP. As quatro portas UDP são usadas para mídia, como áudio e vídeo, para garantir que fluam corretamente.

Abrir essas portas é fundamental para uma implantação confiável do Teams. Bloquear essas portas não é suportado e afeta a qualidade da mídia.

Se a sua organização exigir que você especifique o intervalo de endereços IP e os domínios para os quais essas portas devem ser abertas, você poderá restringir os intervalos de IP e os domínios de destino para essas portas. Para obter uma lista de portas, protocolos e intervalos de IP exatos, consulte [URLs e intervalos de endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Se você optar por restringir os intervalos de endereço IP e os domínios de destino, você precisará manter atualizada a lista de portas e intervalos, pois eles podem ser alterados. Você pode se inscrever [neste feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para ser atualizado quando ocorrerem mudanças. Também é uma boa prática testar se todas as portas estão abertas executando a [Ferramenta de avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) regularmente. Você pode saber mais sobre a funcionalidade dessa ferramenta na próxima seção.

No caso de um servidor proxy ser implantado, recomendamos que você desvie o servidor proxy para todos os serviços do Teams. Embora o uso de um proxy possa funcionar, é muito provável que a qualidade seja reduzida devido ao fato de a mídia ser forçada a usar TCP em vez de UDP. Para obter mais informações sobre servidores proxy e desvios, consulte [URLs e intervalos de endereço IP do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Considerações de rede adicionais
### <a name="external-name-resolution"></a>Resolução do nome externo

Certifique-se de que todos os computadores cliente que executam o cliente Teams possam resolver consultas externas de DNS para descobrir os serviços fornecidos pelo Office 365.

### <a name="nat-pool-size"></a>Tamanho do pool de NAT

Quando vários usuários e dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.

Para reduzir esse risco, garanta que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas. O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectar aos serviços do Office 365. Para mais informações, consulte [Suporte de NAT com o Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Detecção de intrusões e guia de prevenção

Se o seu ambiente tiver um sistema de detecção de intrusões e/ou sistema de prevenção de intrusões implantado para uma camada extra de segurança para conexões de saída, verifique se o tráfego que tem URLs do Office 365 como destino está na lista de permissões.

## <a name="test-the-network"></a>Testar a rede

Depois de concluir o planejamento e a preparação da rede, inclusive a atualização da largura de banda e a abertura de portas no firewall, será necessário testar o desempenho da rede. Os resultados do teste darão uma ideia mais clara da otimização ou da remediação necessária da rede para o sucesso da implementação do Teams.

É possível baixar a [Ferramenta de avaliação de ree do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está ou não pronta para o Teams. A ferramenta oferece dupla funcionalidade: ela pode testar se todas as portas corretas foram abertas e pode testar falhas de rede.

Depois de baixar e instalar a ferramenta, você poderá encontrá-la em C:\\Arquivos de Programas\\Ferramenta de avaliação de rede do Microsoft Skype for Business. Um guia detalhado sobre como usar a ferramenta (Usage.docx) está incluído no diretório.

### <a name="test-for-opened-ports"></a>Testar portas abertas

Abra uma janela de prompt de comando e vá até o diretório da Ferramenta de avaliação de rede acessando **cd C:\\Arquivos de Programas\\Ferramenta de avaliação de rede do Microsoft Skype for Business**. No prompt de comando, inicie o teste de portas abertas inserindo **networkassessmenttool.exe /connectivitycheck**

Depois de executar as verificações, a ferramenta exibirá a mensagem “Verificações concluídas com sucesso” ou relatará as portas que estavam bloqueadas. Isso também gera um arquivo chamado Connectivity_results.txt, que contém o resultado da ferramenta e fica armazenado em %userprofile%\\appdata\\local\\ferramenta de avaliação de rede do microsoft skype for business\\ diretório.

Recomendamos a execução das verificações de conectividade regularmente para verificar se as portas foram abertas e estão funcionando corretamente.

### <a name="test-for-network-impairments"></a>Testar falhas de rede

Para aumentar a satisfação do usuário, você deve limitar as falhas de rede. As falhas de rede mais comuns são atraso (latência), perda de pacote e tremulação:

-   **Latência:** é o tempo necessário para levar um pacote IP do ponto A para o ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como tempo resposta ou unidirecional.

-   **Perda de pacote**: costuma ser definida como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacote afeta diretamente a qualidade do áudio, desde pequenos pacotes individuais perdidos que quase não afetam as perdas de pacote de intermitência back-to-back, provocando o corte completo do áudio.

-   **Tremulação de chegada entre pacotes ou, simplesmente, tremulação:** é a alteração média de atraso entre os pacotes sucessivos. A maioria dos softwares VoIP modernos, incluindo o Skype for Business, pode se adaptar a alguns níveis de tremulação através do buffer. É somente quando a tremulação excede o buffer que o participante nota os efeitos da tremulação.

Os valores máximos dessas falhas estão descritos em [Qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Ao testar essas falhas, nós as diferenciamos em dois segmentos separados:

-   O *segmento de borda* é o segmento em que o roteador habita. É o segmento de rede lógica mais próximo conectado à internet em cada um dos seus locais. Na maioria dos casos, é o ponto de conexão do roteador ou, possivelmente, uma rede de perímetro (também conhecida como *DMZ*, *zona desmilitarizada* e *sub-rede filtrada*). Entre esse segmento e a internet, não deve ocorrer nenhum outro tráfego que afete outros dispositivos além do roteador.

-   O *segmento do cliente* é o segmento de rede lógica em que seus clientes residem.

É necessário testar os dois segmentos usando a Ferramenta de avaliação de rede. Para testar o segmento, navegue até o diretório e insira **networkassessmenttool.exe** no prompt de comando. Os resultados são gravados em um arquivo chamado Results.tsv e você pode compará-los aos [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de cada segmento.

Observe que ambos os segmentos devem atender aos requisitos de uma implantação de alta qualidade. Recomendamos que você execute a ferramenta várias vezes durante uma hora completa para ter uma boa indicação do desempenho de sua rede.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correção de rede

Se os resultados do planejamento de largura de banda, testes de porta ou testes de requisitos de rede mostrarem que a rede atual precisa de correção antes de implantar o Teams, isso poderá ser feito de várias maneiras: 

-   Para largura de banda insuficiente, atualize as conexões para que o tráfego para o Office 365 possa fluir sem impedimentos.

-   Para portas bloqueadas, altere as regras de firewall e teste-as novamente.

-   Para falhas de rede, sempre execute uma análise da causa raiz.

A qualidade de serviço (QoS) pode ser usada para combater as falhas ao priorizar e separar o tráfego. Algumas organizações optam por implantar a QoS para superar problemas de largura de banda ou restringir a quantidade de fluxo de tráfego. Isso não melhora a qualidade e causa novos problemas. Uma análise de causa raiz sempre deve ser realizada quando as falhas de rede excederem os requisitos. A QoS pode ser uma solução. Para obter mais informações, consulte [Qualidade de Serviço no Microsoft Teams](qos-in-teams.md).

>[!NOTE]
>Muitas redes evoluem ao longo do tempo devido a atualizações, expansões ou outros requisitos empresariais. Verifique se você tem processos operacionais em vigor para manter essas áreas como parte do planejamento do gerenciamento do serviço.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Ponto de decisão</td><td><ul><li>Quem será o responsável por realizar as devidas avaliações de rede em todos os segmentos de rede e locais da organização?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Você pode realizar uma avaliação detalhada da rede para ajudar a garantir que sua rede esteja pronta para a implantação do Microsoft Teams. Para obter mais informações, consulte [Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Execute a correção de rede com base nos resultados da avaliação de prontidão de rede para cada segmento de rede.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Principais conclusões

Seguem as principais conclusões desta orientação. Você deve:

-   Abra as portas TCP 80 e 443 de saída dos clientes que usarão o Teams.

-   Abra portas UDP 3478 a 3481 de saída dos clientes que usarão o Teams.

-   Certifique-se de ter largura de banda suficiente para implantar o Teams, completando o [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Execute a [Ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) e certifique-se de atender aos requisitos descritos em [Qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) tanto para o segmento de borda, como para o segmento do cliente.
