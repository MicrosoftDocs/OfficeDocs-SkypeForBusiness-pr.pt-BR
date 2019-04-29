---
title: Avalie seu ambiente para as cargas de trabalho do cloud voice do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use personagens e análise de rede para avaliar a preparação da sua organização, abra as portas TCP e UDP corretas, executar qualquer correção de rede.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f91bde48311e12a6cdac63f7f855b1267b6e1f4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401061"
---
# <a name="evaluate-my-environment"></a>Avaliar meu ambiente

Este artigo fornece uma visão geral dos requisitos de adequadamente avaliando o ambiente atual para o uso de serviços de nuvem de voz. Avaliando seu ambiente, você pode identificar os riscos e os requisitos que influenciam a sua implantação de voz de nuvem geral. Identificando antecipadamente desses itens, você pode ajustar seu planejamento para o sucesso da unidade.

## <a name="introduction-to-evaluating-your-environment"></a>Introdução ao avaliando o ambiente 

Para obter os resultados de chave agregados (OKRs), você fez anteriormente decisões principais de serviço. A próxima etapa é para executar a descoberta do ambiente para avaliar todos os aspectos relacionados à sua equipe de TI e infraestrutura de telefonia, rede e operações para confirmar que sua organização está pronta para implementar a solução.

Descoberta ambiental deve incluir a avaliação de prontidão de rede para garantir que sua rede pode suportar a implementação da conferência de áudio ou sistema telefônico com chamar planejar os serviços.

Você identificar riscos técnicos como parte de uma avaliação do ambiente e avaliação de prontidão de adoção e desenvolver um plano de atenuação para cada risco identificado.
Você deve incorporar essas informações no registrador risco.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Ambiente atual

Como parte do seu ambiente descoberta, incluir todos os assuntos relacionados à computação do usuário final, como uma avaliação de prontidão de PCs e dispositivos móveis para dar suporte a conferência de áudio e o sistema telefônico com chamar planejar business casos de uso, de requisitos de hardware para requisitos de software.

Descoberta do ambiente também poderá revelar se você precisar de [números de telefone de transferência para a Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).
Sabendo disso ajudarão sua organização ajuste seu plano de projeto e preparar as informações necessárias para o número de porta. Você pode usar a [Descoberta ambiental para distribuição de equipes da Microsoft](environmental-discovery-for-microsoft-teams-rollout.md) de MyAdvisor para executar a descoberta ambiental.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável pela conclusão uma avaliação do ambiente?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Os resultados da avaliação do ambiente do documento.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Recursos de avaliação do gerenciamento de adoção e alteração 

Implantação coloca uma nova tecnologia em mãos de um usuário, mas os resultados dos negócios são concretizados somente depois que os usuários realmente adotarem essa solução como seus próprios. Para ajudar a garantir a adoção de uma nova solução sustentada, você precisará enfocam os esforços de preparação do usuário e o gerenciamento de alterações. Para obter melhores resultados, conduzir planejamento como um fluxo de trabalho paralelo às suas atividades de preparação técnica de preparação do usuário e incorporar as seguintes atividades:

-   **Organizacional e da criação de perfil de usuário:** Análise de receptiveness organizacional para alterar além da análise de uso caso e pessoa

-   **Preparação e recursos de preparação:** Criação de direcionado e o alcance de amplo número de divulgação, treinamento e recursos de suporte, incluindo focadas no valor de mensagens para acelerar usuário apoio da direção da

Use as seguintes considerações para avaliar a preparação para a sua organização para o gerenciamento de alterações do usuário de endereço.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Você teve sucesso anterior com a adoção de usuário do software ou serviços?</li><li>É possível controlar a adoção de uso?</li><li>Você tem os recursos para criar e gerenciar uma initial&mdash;e em andamento&mdash;campanha de adoção (divulgação, treinamento e suporte)?</li><li>Você tem uma equipe de gerenciamento de adoção/mudança de usuário dedicada, ou pode investir em desses recursos para garantir resultados de negócios?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Se você respondeu &quot;Sim&quot; para todos os itens acima, identificar participantes do gerenciamento de alteração do usuário à direita e começar seu planejamento de preparação do usuário.</li><li>Se você respondeu &quot;sem&quot; para alguns ou todos os itens acima, considere envolvente fora de recursos para ajudá-lo com orientando o gerenciamento de alterações e atividades relacionadas a adoção para sua organização.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Preparação da rede

Equipes usa o áudio e vídeo tecnologia (codecs) que pode se adaptar a — e, portanto, têm um melhor desempenho em — mais condições de rede. Para garantir o desempenho ideal e consistente, você deve preparar sua rede para equipes.

![Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco na rede.] (media/evaluate-my-environment-image1.png "Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco na rede.")

## <a name="key-takeaways"></a>Principais argumentos

Estes são os argumentos principais desta orientação. Faça o seguinte:

-   Abra as portas TCP 80 e 443 de saída de clientes que usarão as equipes.

-   Abra as portas UDP 3478 por meio de saída 3481 de clientes que usarão as equipes.

-   Certifique-se de que você tenha a largura de banda suficiente para a implantação de equipes, completando o [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Execute a [Ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) e verifique se você atende aos requisitos descritos em [desempenho de conectividade de rede e qualidade de mídia](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) do segmento de borda e o segmento de cliente.

## <a name="why-should-you-prepare-your-network"></a>Por que você deve preparar sua rede?

Antes de observarmos as etapas a serem tomadas, é importante entender o que pode afetar o desempenho das equipes e, portanto, satisfação e felicidade do usuário.
Três áreas principais de risco podem afetar como usuários percebem a qualidade da rede:

-   Largura de banda suficiente disponível

-   Bloqueadores de firewall e proxy

-   Problemas de rede como tremulação e perda de pacote

As etapas descritas a seguir o ajudarão a determinar que se a sua implantação poderá ser afetada por qualquer um desses fatores e ajudará você progride uma resolução.
Falhar preparar sua rede levarão provavelmente aos usuários insatisfeitos e corrige dispendiosa, da ad hoc. Por Otimize sua rede — e a sua organização — para equipes, você pode aumentar drasticamente sua chance de sucesso.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planejamento de largura de banda

A primeira etapa para a preparação da rede é garantir que sua rede tenha largura de banda suficiente disponível para as modalidades que equipes irá fornecer aos usuários. Planejamento da largura de banda suficiente é uma tarefa razoavelmente simples e iniciar uma barreira de muito baixa para garantir que seus usuários terão uma experiência de equipes de alta qualidade.

Você iniciar o seu planejamento de jornada para equipes do [Supervisor de meu site](https://myadvisor.fasttrack.microsoft.com/) usando Planejador de rede de largura de banda. Planejador de rede fornece largura de banda de cada site de planejamento para equipes e oferece recomendações para otimizar o desempenho da rede.

### <a name="local-internet-egress"></a>Saída para a Internet local

Muitas redes foram projetadas para usar uma topologia hub-spoke. Nessa topologia, normalmente o tráfego da Internet percorre a WAN até um data center central antes de exteriorizar-se (sair) na Internet. Muitas vezes, isso é feito para centralizar os dispositivos de segurança de rede a fim de reduzir o custo total.

O tráfego de retorno pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como o Microsoft Teams é executado na ampla rede global da Microsoft, frequentemente há um local de emparelhamento de rede perto do usuário. O usuário provavelmente terá melhor desempenho ao sair de um ponto de Internet local próximo de sua localização e entrar em nossa rede com otimização de voz assim que possível. Para algumas cargas de trabalho, solicitações DNS são usadas para enviar o tráfego para o servidor front-end mais próximo. Nesses casos, é importante que, ao usar um ponto de saída local, ele esteja emparelhado com a resolução de DNS local.

A otimização do caminho de rede para a rede global da Microsoft melhorará o desempenho e, em última instância, oferecerá a melhor experiência para os usuários. Para obter mais detalhes, consulte a postagem no blog [Como obter a melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

As VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, eles estão geralmente não projetados ou configurados para oferecer suporte a mídia em tempo real. Algumas VPNs também podem não dar suporte ao UDP. VPNs também introduzem uma camada adicional de criptografia, na parte superior de tráfego de mídia que já está criptografado. Além disso, a conectividade com o serviço de equipes talvez não seja eficiente devido ao tráfego de fixação de forma por meio de um dispositivo VPN.
Além disso, eles não são necessariamente projetados de uma perspectiva de capacidade para acomodar as cargas antecipadas que precisarão de equipes.

A recomendação é fornecer um caminho alternativo que contorne a VPN para o tráfego do Microsoft Teams. Isso normalmente é conhecido como *divisão de túnel VPN*. Divida encapsulamento significa que o tráfego para o Office 365 não atravessa VPN, mas será levado diretamente para o Office 365. Essa alteração tem um impacto positivo sobre a qualidade, mas também apresenta um benefício secundário de reduzir a carga dos dispositivos de VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

### <a name="wi-fi"></a>Wi-Fi

Como o VPN, redes Wi-Fi não são necessariamente projetadas ou configuradas para oferecer suporte a mídia em tempo real. Planejando ou otimizando, uma rede Wi-Fi para equipes de suporte é uma consideração importante para uma implantação de alta qualidade.

Há vários fatores que entram em cena para otimizar uma rede Wi-Fi:

-   Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

-   Posicionamento de ponto de planejamento e otimizando as faixas Wi-Fi e acesso. O intervalo de 2,4 GHz pode fornecer uma experiência adequada, dependendo do posicionamento do ponto de acesso, mas muitas vezes os pontos de acesso são afetados por outros dispositivos do consumidor que funcionam naquele intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real porque é mais denso, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.

-   Se forem implantados redes Wi-Fi de banda dupla, considere a implementação de direcionamento de banda. O direcionamento de banda é uma técnica implementada por fornecedores de Wi-Fi para influenciar a banda dupla aos clientes utilizarem o intervalo de 5 GHz.

-   Quando os pontos de acesso no mesmo canal estiverem muito juntos, eles podem causar sobreposição de sinal e competem acidentalmente, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso que estão próximas umas das outras estão em canais que não se sobreponham.

Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Recomendamos que você consulte as orientações específicas do fornecedor.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de firewall e proxy

Microsoft Teams se conecta ao Microsoft Online Services e precisa de conectividade de internet para que isso. Para as equipes funcionar corretamente, você deve abrir as portas TCP 80 e 443 dos clientes com a internet e portas UDP 3478 por meio de 3481 dos clientes com a internet. As portas TCP são usadas para se conectar ao conteúdo baseado na web, como o SharePoint Online, o Exchange Online e os serviços de equipes de bate-papo.
Plug-ins e conectores também se conectar por essas portas TCP. Quatro portas UDP são usadas para a mídia, como áudio e vídeo, para garantir que elas fluem corretamente.

Abertura dessas portas é essencial para uma implantação de equipes confiável. Bloquear essas portas não é suportado e terão efeito na qualidade de mídia.

Se sua organização requer que você especifique o exato intervalos de endereços IP e domínios ao qual essas portas devem ser abertas, você pode restringir os domínios para essas portas e intervalos IP de destino. Para obter uma lista de exatas portas, protocolos e intervalos IP, consulte [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Se você escolher restringir os intervalos de endereços IP de destino e os domínios, certifique-se de manter a lista de intervalos de porta e atualizado porque eles podem ser alteradas. Você pode assinar [este RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) para serem atualizadas quando ocorrem alterações. Também é uma boa prática para testar se todas as portas são abertas executando o [Skype para ferramenta de avaliação de rede comercial](https://www.microsoft.com/download/details.aspx?id=53885) regularmente. Você pode encontrar mais informações sobre a funcionalidade dessa ferramenta na próxima seção.

No caso de um servidor de proxy que está sendo implantado, recomendamos que você ignorar o servidor proxy para todos os serviços de equipes. Embora usando um proxy pode funcionar, é bem provável que qualidade será reduzida devido da mídia sendo forçados a usar TCP em vez de UDP. Para obter mais informações sobre os servidores proxy e ignorando, consulte [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Testar a rede

Depois de concluir a preparação de planejamento e rede — incluindo a atualização de largura de banda e abrindo portas no firewall — você deve testar o desempenho da sua rede. Os resultados deste teste será pintar uma imagem mais nítida de qualquer otimização de rede ou remediação necessários para o sucesso do seu áudio da conferência ou o sistema telefônico com implementação chamando planejar.

Você pode baixar o [Skype para ferramenta de avaliação de rede comercial](https://www.microsoft.com/download/details.aspx?id=53885) para testar se a sua rede está pronta para equipes. A ferramenta oferece a funcionalidade dual: ele pode testar se a todas as portas corretas foram abertas e, em seguida, ele pode testar para problemas de rede.

Depois que baixar e instala a ferramenta, você pode encontrá-lo em c:\\Program Files\\Microsoft Skype para ferramenta de avaliação de rede comercial. Uma orientação detalhada sobre como usar a ferramenta, Usage.docx, está incluída nesse diretório.

### <a name="test-for-opened-ports"></a>Teste de portas abertas

Abra uma janela de prompt de comando e navegue até o diretório de rede Assessment Tool, inserindo **cd c:\\Program Files\\Microsoft Skype para ferramenta de avaliação de rede comercial**. No prompt de comando, inicie o teste de portas abertos inserindo o **networkassessmenttool.exe /connectivitycheck**

Depois de executar as verificações, a ferramenta irá exibir a mensagem "Verificações concluído com êxito" ou enviar relatórios sobre as portas que foram bloqueadas.
Ele também gera um arquivo chamado Connectivity_results.txt, que contém a saída da ferramenta e armazena-o na pasta % userprofile %\\appdata\\local\\microsoft Skype para ferramenta de avaliação de rede comercial\\ directory.

Recomendamos que você execute as verificações de conectividade regularmente para garantir que as portas foram abertas e estão funcionando corretamente.

### <a name="test-for-network-impairments"></a>Teste de problemas de rede

Para aumentar a satisfação do usuário, você deve limitar quaisquer deficiências em sua rede.
Os problemas de rede mais comuns são atraso (latência), perda de pacote e tremulação:

-   **Latência:** Esse é o tempo que leva para obter um pacote IP do ponto A ponto b na rede. Esse atraso de propagação de rede essencialmente está vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional tomada por vários roteadores entre si.
    Latência é medida como tempo unidirecional ou de ida e volta.

-   **Perda de pacotes**: isso geralmente é definido como uma porcentagem de pacotes que são perdidos em uma determinada janela de tempo. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos tendo quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.

-   **Tremulação de chegada de pacotes entre ou simplesmente tremulação:** Esta é a média alteração em atraso entre pacotes sucessivos. Mais moderno software de VoIP, incluindo Skype para os negócios, pode se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante perceberá os efeitos de variação.

Os valores máximos para esses problemas são descritos no [desempenho de conectividade de rede e qualidade de mídia](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Quando o teste esses problemas, podemos distinguir entre dois segmentos separados:

-   O *segmento de borda* é o segmento na qual reside o seu roteador. Esse é o segmento de rede lógica mais próximo conectado à internet em cada um dos seus locais. Na maioria dos casos, esse é o ponto de conexão do roteador ou, possivelmente, em uma rede de perímetro (também conhecida como *DMZ*, *zona desmilitarizada*e *sub-rede filtrada*). Nenhum tráfego adicional que afeta os dispositivos que não seja o roteador deve ocorrer entre esse segmento e a internet.

-   O *segmento de cliente* é o segmento de rede lógica nos quais residem os seus clientes.

Você deve testar os dois segmentos usando a ferramenta de avaliação de rede. Para testar o segmento, navegue até o diretório e insira **networkassessmenttool.exe** no prompt de comando. Os resultados são gravados em um arquivo chamado Results.tsv e compará-los com os [requisitos](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para cada segmento.

Observe que os dois segmentos devem cumprir os requisitos para uma implantação de alta qualidade. Recomendamos que você execute a ferramenta várias vezes por uma hora diretamente para fazer uma boa indicação de desempenho da sua rede.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correção de rede

Se os resultados do planejamento de largura de banda, testes de porta ou requisitos de rede testes mostram que sua rede atual precisa remediação antes de implantar equipes, isso pode ser feito de várias maneiras:

-   Para a largura de banda insuficiente, sem conexões para que o tráfego para o Office 365 pode fluir demora de atualização.

-   Para portas bloqueadas, altere as regras de firewall e teste novamente as portas.

-   Para problemas de rede, execute sempre uma análise de causa raiz.

Qualidade de serviço (QoS) pode ser usado para deficiências batalha priorização e separando o tráfego. Algumas organizações optam por implantar o QoS para superar os problemas de largura de banda ou restringir a quantidade de fluxo de tráfego. Isso não melhorar a qualidade e levarão à redução novos problemas. Uma análise de causa raiz deve ser sempre executada quando os problemas de rede excedem requisitos. QoS pode ser uma solução.
Para obter mais informações, consulte [Qualidade de serviço em equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>Muitas redes evoluem ao longo do tempo devido a atualizações, expansões ou outros requisitos empresariais. Verifique se você tem processos operacionais em vigor para manter essas áreas como parte do planejamento do gerenciamento do serviço.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Quem será responsável pela conclusão de avaliações de rede adequado entre todos os segmentos de rede e locais da organização?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li>Você pode executar uma avaliação de rede detalhado para ajudar a garantir que sua rede está pronta para sua implantação do Microsoft Teams. Para obter mais informações, consulte <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Avaliação de prontidão de rede</a>.</li><li>Execute a correção de rede com base nos resultados da avaliação de prontidão da rede para cada segmento de rede.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->