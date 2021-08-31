---
title: Avaliar seu ambiente para cargas de trabalho de voz na nuvem
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use personas e análise de rede para avaliar a preparação da sua organização, abrir as portas TCP e UDP corretas, executar qualquer correção de rede.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0fbbc32c1a22fb5a2144231964b8498291ca009d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730720"
---
# <a name="evaluate-my-environment"></a>Avaliar meu ambiente

Este artigo fornece uma visão geral dos requisitos para avaliar corretamente seu ambiente atual para o uso de serviços de voz na nuvem. Ao avaliar seu ambiente, você identifica riscos e requisitos que influenciarão sua implantação geral de voz na nuvem. Ao identificar esses itens antecipadamente, você pode ajustar seu planejamento para impulsionar o sucesso.

## <a name="introduction-to-evaluating-your-environment"></a>Introdução à avaliação do seu ambiente

Para obter seus principais resultados (OKRs) objetivos, você já tomou decisões importantes de serviço. A próxima etapa é realizar a descoberta ambiental para avaliar todos os aspectos relacionados à infraestrutura de TI e telefonia, rede e operações para confirmar se sua organização está pronta para implementar a solução.

A descoberta ambiental deve incluir a avaliação de preparação de rede para garantir que sua rede possa dar suporte à implementação da Audioconferência ou Sistema de Telefonia com serviços de Plano de Chamada.

Você identifica os riscos técnicos como parte de uma avaliação de avaliação ambiental e preparação de adoção e desenvolve um plano de mitigação para cada risco identificado.
Você deve incorporar essas informações no registro de riscos.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Ambiente atual

Como parte de sua descoberta ambiental, inclua todas as questões relacionadas à computação do usuário final, como uma avaliação de prontidão de PCs e dispositivos móveis para dar suporte a Audioconferência e Sistema de Telefonia com casos de uso de negócios do Plano de Chamada, desde requisitos de hardware até requisitos de software.

A descoberta ambiental também pode descobrir se você precisa transferir [números de telefone para a Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
Saber isso ajudará sua organização a ajustar seu plano de projeto de acordo e preparar as informações necessárias para a portação de números. Você pode usar a [descoberta ambiental para Microsoft Teams para](environmental-discovery-for-microsoft-teams-rollout.md) executar a descoberta ambiental.

<table>
<tr><td>Título</td><td>Descrição</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Who será responsável por concluir uma avaliação de ambiente?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Documente os resultados da avaliação do ambiente.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Recursos de avaliação de gerenciamento de alterações e adoção

A implantação coloca uma nova tecnologia na ponta dos dedos de um usuário, mas os resultados comerciais só são percebidos depois que os usuários realmente adotam essa solução como sua própria. Para ajudar a garantir a adoção sustentada de uma nova solução, você precisará concentrar seus esforços na preparação do usuário e no gerenciamento de alterações. Para obter resultados ideais, conduza o planejamento de preparação do usuário como um fluxo de trabalho paralelo às suas atividades de preparação técnica e incorpore as seguintes atividades:

-   **Criação de perfil organizacional e de usuário:** Análise da receptividade organizacional a alterações, além de usar análise de caso e persona

-   **Preparação e preparação de recursos:** Criação de recursos de reconhecimento, treinamento e suporte direcionados e de amplo alcance, incluindo mensagens de valor focado para acelerar a compra do usuário

Use as considerações a seguir para avaliar a preparação da sua organização para lidar com o gerenciamento de alterações do usuário.

<table>
<tr><td>Título</td><td>Descrição</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Você já teve sucesso anterior com a adoção de software ou serviços pelo usuário?</li><li>Você pode rastrear a captação de uso?</li><li>Você tem recursos para projetar e gerenciar uma campanha de adoção inicial e &mdash; &mdash; contínua (reconhecimento, treinamento e suporte)?</li><li>Você tem uma equipe de gerenciamento de alterações/adoção de usuários dedicada ou pode investir nesses recursos para garantir resultados comerciais?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Se você respondeu sim a todos os acima, identifique os participantes de gerenciamento de alterações de usuário corretos e inicie o planejamento &quot; &quot; de preparação do usuário.</li><li>Se você respondeu não a alguns ou a todos os recursos acima, considere envolver recursos externos para ajudar a impulsionar o gerenciamento de alterações e atividades relacionadas à adoção &quot; &quot; para sua organização.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Preparação da rede

O Teams usa tecnologia de áudio e vídeo (codecs) que pode se adaptar à maioria das condições de rede e, portanto, tem um melhor desempenho nelas. Para garantir um desempenho ideal e consistente, você deve preparar sua rede para o Teams.

![Diagrama que descreve os três componentes de qualidade.](media/evaluate-my-environment-image1.png "Diagrama que descreve os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco na rede.")

## <a name="key-takeaways"></a>Principais conclusões

Seguem as principais conclusões desta orientação. Você deve:

-   Abra as portas TCP 80 e 443 de saída dos clientes que usarão o Teams.

-   Abra portas UDP 3478 a 3481 de saída dos clientes que usarão o Teams.

-   Certifique-se de ter largura de banda suficiente para implantar o Teams.

-   Execute a [Ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) e certifique-se de atender aos requisitos descritos em [Qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) tanto para o segmento de borda, como para o segmento do cliente.

## <a name="why-should-you-prepare-your-network"></a>Por que você precisa preparar sua rede?

Antes de vermos as etapas a serem tomadas, é importante compreender o que pode afetar o desempenho da Teams e, assim, a satisfação e a satisfação do usuário.
As três principais áreas de risco podem afetar como os usuários percebem a qualidade de rede:

-   Largura de banda insuficiente disponível

-   Bloqueadores de firewall e proxy

-   Deficiências de rede, como tremulação e perda de pacotes

As etapas descritas abaixo ajudarão você a verificar se sua implantação pode ser afetada por algum desses fatores e a progredir para uma solução.
Provavelmente, se deixar de preparar sua rede, os usuários ficarão insatisfeitos e haverá correções ad-hoc dispendiosas. Ao preparar sua rede e sua organização para o Teams, você pode aumentar significativamente sua chance de sucesso.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planejamento de largura de banda

A primeira etapa para a preparação da rede é garantir que sua rede tenha largura de banda suficiente disponível para as modalidades Teams fornecer aos usuários. O planejamento de largura de banda suficiente é uma tarefa bastante simples e um início de barreira muito baixo para garantir que os usuários tenham uma experiência de Teams alta qualidade.

### <a name="local-internet-egress"></a>Saída para a Internet local

Muitas redes foram projetadas para usar uma topologia hub-spoke. Nessa topologia, normalmente o tráfego da Internet percorre a WAN até um data center central antes de exteriorizar-se (sair) na Internet. Muitas vezes, isso é feito para centralizar os dispositivos de segurança de rede a fim de reduzir o custo total.

O tráfego de retorno pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como Microsoft Teams é executado na grande rede global da Microsoft, geralmente há um local de peering de rede próximo ao usuário. O usuário provavelmente terá melhor desempenho ao sair de um ponto de Internet local próximo de sua localização e entrar em nossa rede com otimização de voz assim que possível. Para algumas cargas de trabalho, solicitações DNS são usadas para enviar o tráfego para o servidor front-end mais próximo. Nesses casos, é importante que, ao usar um ponto de saída local, ele seja emparelhado com a resolução DNS local.

Otimizar o caminho de rede para a rede global da Microsoft melhorará o desempenho e, em última análise, fornecerá a melhor experiência para os usuários. Para obter mais detalhes, consulte a postagem no blog [Como obter a melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

As VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, eles geralmente não são projetados ou configurados para dar suporte a mídia em tempo real. Algumas VPNs também podem não dar suporte ao UDP. As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado. Além disso, a conectividade com o serviço do Teams pode não ser eficiente devido ao tráfego excessivo por meio de um dispositivo VPN.
Além disso, eles não são necessariamente projetados de uma perspectiva de capacidade para acomodar as cargas previstas que Teams exigir.

A recomendação é fornecer um caminho alternativo que contorne a VPN para o tráfego do Microsoft Teams. Geralmente, isso é conhecido como *VPN de túnel dividido*. O túnel dividido significa que o tráfego para Microsoft 365 ou Office 365 não percorrerá a VPN, mas irá diretamente para Microsoft 365 ou Office 365. Essa alteração terá um impacto positivo na qualidade, mas também fornece o benefício secundário de reduzir a carga dos dispositivos VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

### <a name="wi-fi"></a>Wi-Fi

Assim como a VPN, Wi-Fi redes não são necessariamente projetadas ou configuradas para dar suporte a mídia em tempo real. Planejar ou otimizar uma rede Wi-Fi para oferecer suporte ao Teams é uma consideração importante para uma implantação de alta qualidade.

Existem vários fatores que entram em cena para otimizar uma rede Wi-Fi:

-   Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

-   Planejar e otimizar as bandas de Wi-Fi e a colocação do ponto de acesso. O intervalo de 2,4 GHz pode fornecer uma experiência adequada, dependendo do posicionamento do ponto de acesso, mas muitas vezes os pontos de acesso são afetados por outros dispositivos do consumidor que funcionam naquele intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real porque é mais denso, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.

-   Se redes Wi-Fi de banda dupla forem implantadas, considere implementar a direção de banda. A direção de banda é uma técnica implementada por fornecedores de Wi-Fi para influenciar os clientes de banda dupla a usar o intervalo de 5 GHz.

-   Quando pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e competir involuntariamente, resultando em uma experiência deficiente para o usuário. Certifique-se de que os pontos de acesso próximos um do outro estejam em canais que não se sobreponham.

Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Recomendamos que você consulte as orientações específicas do fornecedor.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de proxy e firewall

O Microsoft Teams se conecta ao Microsoft Online Services e, para isso, precisa de conectividade com a Internet. Para que o Teams funcione corretamente, é preciso abrir as portas TCP 80 e 443 dos clientes para a internet e as portas UDP 3478 a 3481 dos clientes para a internet. As portas TCP são usadas para conexão a conteúdo baseado na web, como o SharePoint Online, o Exchange Online e os serviços de bate-papo do Teams.
Plugins e conectores também se conectam por essas portas TCP. As quatro portas UDP são usadas para mídia, como áudio e vídeo, para garantir que fluam corretamente.

Abrir essas portas é fundamental para uma implantação confiável do Teams. O bloqueio dessas portas não é compatível e terá efeito na qualidade da mídia.

Se a sua organização exigir que você especifique o intervalo de endereços IP e os domínios para os quais essas portas devem ser abertas, você poderá restringir os intervalos de IP e os domínios de destino para essas portas. Para uma lista de portas, protocolos e intervalos IP exatos, consulte [Microsoft 365 ou Office 365 URLs e intervalos de endereços IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Se você optar por restringir os intervalos de endereço IP e os domínios de destino, você precisará manter atualizada a lista de portas e intervalos, pois eles podem ser alterados. Você pode se inscrever [neste feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para ser atualizado quando ocorrerem mudanças. Também é uma boa prática testar se todas as portas são abertas executando a Ferramenta Skype for Business [de](https://www.microsoft.com/download/details.aspx?id=53885) Avaliação de Rede regularmente. Você pode saber mais sobre a funcionalidade dessa ferramenta na próxima seção.

No caso de um servidor proxy ser implantado, recomendamos que você desvie o servidor proxy para todos os serviços do Teams. Embora o uso de um proxy possa funcionar, é muito provável que a qualidade seja reduzida devido à força da mídia usar tCP em vez de UDP. Para obter mais informações sobre servidores proxy e ignorar, consulte [Microsoft 365 ou Office 365 URLs e intervalos de endereços IP.](./office-365-urls-ip-address-ranges.md)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Testar a rede

Depois de concluir o planejamento e a preparação da rede, incluindo a atualização da largura de banda e a abertura de portas no firewall, você deve testar o desempenho da rede. Os resultados desse teste pintarão uma imagem mais clara de qualquer otimização de rede ou correção necessária para o sucesso da sua Audioconferência ou Sistema de Telefonia com a implementação do Plano de Chamada.

É possível baixar a [Ferramenta de avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está ou não pronta para o Teams. A ferramenta oferece dupla funcionalidade: ela pode testar se todas as portas corretas foram abertas e pode testar falhas de rede.

Depois de baixar e instalar a ferramenta, você poderá encontrá-la em C: Arquivos de Programas Microsoft Skype for Business Ferramenta de \\ \\ Avaliação de Rede. Um guia detalhado sobre como usar a ferramenta (Usage.docx) está incluído no diretório.

### <a name="test-for-opened-ports"></a>Testar portas abertas

Abra uma janela de prompt de comando e navegue até o diretório Ferramenta de Avaliação de Rede inserindo cd C: Arquivos de Programas **Microsoft Skype for Business Ferramenta de \\ \\ Avaliação de Rede**. No prompt de comando, inicie o teste de portas abertas inserindo **networkassessmenttool.exe /connectivitycheck**

Depois de executar as verificações, a ferramenta exibirá a mensagem "Verificações Concluídas com Êxito" ou relatará as portas que foram bloqueadas.
Isso também gera um arquivo chamado Connectivity_results.txt, que contém o resultado da ferramenta e fica armazenado em %userprofile%\\appdata\\local\\ferramenta de avaliação de rede do microsoft skype for business\\ diretório.

Recomendamos a execução das verificações de conectividade regularmente para verificar se as portas foram abertas e estão funcionando corretamente.

### <a name="test-for-network-impairments"></a>Testar falhas de rede

Para aumentar a satisfação do usuário, você deve limitar as falhas de rede.
As falhas de rede mais comuns são atraso (latência), perda de pacote e tremulação:

-   **Latência:** é o tempo necessário para levar um pacote IP do ponto A para o ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários.
    A latência é medida como tempo resposta ou unidirecional.

-   **Perda de pacote**: costuma ser definida como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacote afeta diretamente a qualidade do áudio, desde pequenos pacotes individuais perdidos que quase não afetam as perdas de pacote de intermitência back-to-back, provocando o corte completo do áudio.

-   **Tremulação de chegada entre pacotes ou, simplesmente, tremulação:** é a alteração média de atraso entre os pacotes sucessivos. A maioria dos softwares VoIP modernos, incluindo o Skype for Business, pode se adaptar a alguns níveis de tremulação através do buffer. É somente quando a tremulação excede o buffer que o participante nota os efeitos da tremulação.

Os valores máximos dessas falhas estão descritos em [Qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Ao testar essas falhas, nós as diferenciamos em dois segmentos separados:

-   O *segmento de borda* é o segmento em que o roteador habita. É o segmento de rede lógica mais próximo conectado à internet em cada um dos seus locais. Na maioria dos casos, é o ponto de conexão do roteador ou, possivelmente, uma rede de perímetro (também conhecida como *DMZ*, *zona desmilitarizada* e *sub-rede filtrada*). Entre esse segmento e a internet, não deve ocorrer nenhum outro tráfego que afete outros dispositivos além do roteador.

-   O *segmento do cliente* é o segmento de rede lógica em que seus clientes residem.

É necessário testar os dois segmentos usando a Ferramenta de avaliação de rede. Para testar o segmento, navegue até o diretório e insira **networkassessmenttool.exe** no prompt de comando. Os resultados são gravados em um arquivo chamado Results.tsv, e você pode compará-los aos [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de cada segmento.

Observe que ambos os segmentos devem atender aos requisitos de uma implantação de alta qualidade. Recomendamos que você execute a ferramenta várias vezes por uma hora seguida para obter uma boa indicação do desempenho da sua rede.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correção de rede

Se os resultados do planejamento de largura de banda, testes de porta ou testes de requisitos de rede mostrarem que a rede atual precisa de correção antes de implantar o Teams, isso poderá ser feito de várias maneiras:

-   Para largura de banda insuficiente, atualize conexões para que o tráfego Microsoft 365 ou Office 365 possa fluir sem limitação.

-   Para portas bloqueadas, altere as regras de firewall e teste-as novamente.

-   Para falhas de rede, sempre execute uma análise da causa raiz.

A qualidade de serviço (QoS) pode ser usada para combater as falhas ao priorizar e separar o tráfego. Algumas organizações optam por implantar a QoS para superar problemas de largura de banda ou restringir a quantidade de fluxo de tráfego. Isso não melhorará a qualidade e causará novos problemas. Uma análise de causa raiz sempre deve ser realizada quando as falhas de rede excederem os requisitos. A QoS pode ser uma solução.
Para obter mais informações, consulte [Qualidade de Serviço no Microsoft Teams](./qos-in-teams.md).

>[!NOTE]
>Muitas redes evoluem ao longo do tempo devido a atualizações, expansões ou outros requisitos empresariais. Verifique se você tem processos operacionais em vigor para manter essas áreas como parte do planejamento do gerenciamento do serviço.


<table>
<tr><td>Título</td><td>Descrição</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Quem será o responsável por realizar as devidas avaliações de rede em todos os segmentos de rede e locais da organização?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Você pode realizar uma avaliação detalhada da rede para ajudar a garantir que sua rede esteja pronta para a implantação do Microsoft Teams.</li><li>Execute a correção de rede com base nos resultados da avaliação para cada segmento de rede.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->