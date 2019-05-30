---
title: Preparar sua rede para o Microsoft Teams |  Requisitos de firewall de portabilidade
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use essas orientações para preparar sua rede para a implantação e a distribuição do Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eae5cdda83c6d480951c8e370b0d445de6afbc93
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548617"
---
![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica] (media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme se você concluiu essas atividades dos estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Assista à sessão a seguir para saber como o Microsoft Teams aproveita a sua rede e como planejar melhor a conectividade de rede ideal: [planejamento de rede](https://aka.ms/teams-networking) do teams

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Preparar sua rede para a atualização para o Microsoft Teams

Se você estiver implantando áudio, vídeo ou reuniões, poderá realizar algumas etapas adicionais para otimizar sua rede para essa funcionalidade. O Microsoft Teams usa a tecnologia de áudio e de vídeo (codecs) que pode se adaptar e, portanto, executar melhor em: a maioria das condições da rede. Para garantir o desempenho ideal e consistente, você deve preparar a rede para o Microsoft Teams.

![Diagrama descrevendo os três componentes de qualidade] (media/evaluate-my-environment-image1.png "Diagrama descrevendo os três componentes de qualidade e como o gerenciamento de serviços se sobrepõe a todos os três componentes. Com foco na rede.")

## <a name="why-should-you-prepare-your-network"></a>Por que você deve preparar sua rede?

Antes de examinarmos as etapas a serem seguidas, é importante entender o que pode afetar o desempenho do Teams e, conseqüentemente, do usuário e da satisfação do usuário. Três áreas principais de risco podem afetar como os usuários percebem a qualidade da rede:

- Largura de banda insuficiente disponível

- Bloqueadores de firewall e proxy

- Deficiências de rede, como tremulação e perda de pacote

As etapas descritas abaixo ajudarão você a determinar se sua implantação pode ser afetada por qualquer um desses fatores e ajudará você a se mover em direção a uma resolução. A falha na preparação da rede provavelmente levará a usuários insatisfeitos e correções dispendiosas e caras. Ao preparar sua rede, e sua organização, para o Teams, você pode aumentar consideravelmente a chance de sucesso.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planejamento de largura de banda

O Microsoft Teams oferece a melhor experiência de áudio, vídeo e compartilhamento de conteúdo, independentemente das condições da rede. Com os codecs variáveis, a mídia pode ser negociada em ambientes limitados de largura de banda com impacto mínimo. Mas onde a largura de banda não é uma preocupação, as experiências podem ser otimizadas para qualidade, incluindo até 1080p de resolução de vídeo, até 30 qps para vídeo e 15fps para conteúdo e áudio de alta fidelidade.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>Saída para a Internet local

Muitas redes foram projetadas para usar uma topologia hub-spoke. Nessa topologia, normalmente o tráfego da Internet percorre a WAN até um data center central antes de exteriorizar-se (sair) na Internet. Muitas vezes, isso é feito para centralizar os dispositivos de segurança de rede a fim de reduzir o custo total.

O tráfego de retorno pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como o Microsoft Teams é executado na ampla rede global da Microsoft, frequentemente há um local de emparelhamento de rede perto do usuário. O usuário provavelmente terá melhor desempenho ao sair de um ponto de Internet local próximo de sua localização e entrar em nossa rede com otimização de voz assim que possível. Para algumas cargas de trabalho, solicitações DNS são usadas para enviar o tráfego para o servidor front-end mais próximo. Nesses casos, é importante que, ao usar um ponto de saída local, ele esteja emparelhado com a resolução de DNS local.

A otimização do caminho de rede para a rede global da Microsoft melhorará o desempenho e, em última instância, oferecerá a melhor experiência para os usuários. Para obter mais detalhes, consulte a postagem no blog [Como obter a melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Para obter uma experiência ideal ao usar mídia em tempo real no Microsoft Teams, você deve atender aos requisitos de rede do Office 365. Para obter mais informações, consulte [qualidade de mídia e desempenho de conectividade de rede para o Skype for Business online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Os dois que definem segmentos de rede (cliente para Microsoft Edge e Edge do cliente para Microsoft Edge) devem atender aos seguintes requisitos:

|**Valor** |**Cliente para Microsoft Edge** |**Borda do cliente ao Microsoft Edge** |
|---|---|---|
|**Latência (de uma maneira)** |< 50 ms |< 30 ms |
|**Latência (tempo de ida e volta ou RTT)** |< 100 ms |< 60 MS |
|**Perda de pacote intermitente** |<10% durante qualquer 200-MS Interval |<1% durante qualquer 200-MS Interval |
|**Perda de pacote** |<1% durante qualquer intervalo de 15 segundos |< 0,1% durante qualquer intervalo de 15 segundos |
|**Tremulação entre entradas do pacote** |<30 MS durante qualquer intervalo de 15 segundos |<15 MS durante qualquer intervalo de 15 segundos |
|**Reordenação de pacotes** |< 0,05% fora da ordem dos pacotes |< 0,01% fora da ordem dos pacotes |

Para testar ambos os segmentos de rede, você pode usar a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada diretamente no PC cliente e em um PC conectado à borda de rede do cliente. A ferramenta inclui documentação limitada, mas uma documentação mais profunda sobre o uso da ferramenta pode ser encontrada aqui: [avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800). Ao executar esta avaliação de preparação de rede, você pode validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Esta é a mesma avaliação de prontidão de rede que recomendamos ser executada por clientes que pretendem implantar o Skype for Business com êxito.

### <a name="vpn"></a>VPN

As VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, normalmente não são projetados ou configurados para dar suporte a mídia em tempo real. Algumas VPNs também podem não dar suporte ao UDP. As VPNs também introduzem uma camada adicional de criptografia na parte superior do tráfego de mídia que já está criptografado. Além disso, a conectividade com o serviço Teams pode não ser eficiente devido ao tráfego de cabelo de cabelo por meio de um dispositivo VPN. Além disso, eles não são necessariamente projetados a partir de uma perspectiva de capacidade para acomodar as cargas previstas que as equipes precisarão.

A recomendação é fornecer um caminho alternativo que contorne a VPN para o tráfego do Microsoft Teams. Isso normalmente é conhecido como *VPN de encapsulamento dividido*. Tunelamento dividido significa que o tráfego do Office 365 não atravessa a VPN, mas vai diretamente para o Office 365. Essa alteração tem um impacto positivo sobre a qualidade, mas também apresenta um benefício secundário de reduzir a carga dos dispositivos de VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

### <a name="wi-fi"></a>Wi-Fi

Como as redes VPN, Wi-Fi não são necessariamente projetadas ou configuradas para dar suporte à mídia em tempo real. Planejar ou otimizar uma rede Wi-Fi para dar suporte a equipes é uma consideração importante para uma implantação de alta qualidade.

Há vários fatores que entram em cena para otimizar uma rede Wi-Fi:

- Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

- Planejamento e otimização de faixas de Wi-Fi e posicionamento de ponto de acesso. A faixa de 2,4 GHz pode oferecer uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso são geralmente afetados por outros dispositivos de consumo que operam nesse intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real porque é mais denso, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.

- Se redes Wi-Fi de banda dupla forem implantadas, considere a implementação do direcionamento de banda. _Direcionamento de banda_ é uma técnica implementada por fornecedores Wi-Fi para influenciar clientes de banda dupla para usar o intervalo de 5 GHz.

- Quando pontos de acesso do mesmo canal estiverem muito próximos juntos, eles podem causar sobreposição de sinais e, por acaso, competir, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso próximos uns dos outros estejam em canais que não se sobreponham.

Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Recomendamos que você consulte as orientações específicas do fornecedor.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de firewall e proxy

O Microsoft Teams conecta-se aos serviços online da Microsoft e precisa de conectividade com a Internet para isso. Para que as equipes funcionem corretamente, você deve abrir as portas TCP 80 e 443 dos clientes para a Internet e as portas UDP 3478 a 3481 dos clientes para a Internet. As portas TCP são usadas para se conectar ao conteúdo baseado na Web, como o SharePoint Online, o Exchange Online e os serviços de chat de equipe. Plug-ins e conectores também se conectam por essas portas TCP. As quatro portas UDP são usadas para mídia, como áudio e vídeo, para garantir que elas fluam corretamente.

Abrir essas portas é essencial para uma implantação de equipes confiáveis. Não há suporte para o bloqueio dessas portas, e a qualidade da mídia será afetada.

Se a sua organização exigir que você especifique os intervalos de endereços IP e os domínios exatos para os quais essas portas devem ser abertas, você pode restringir os intervalos de IP de destino e domínios para essas portas. Para obter uma lista de portas, protocolos e intervalos de IP exatos, consulte [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Se optar por restringir os intervalos de endereços IP de destino e os domínios, você deverá manter a lista de portas e os intervalos atualizados porque eles podem mudar. Você pode assinar [este RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) para ser atualizado quando ocorrerem alterações. Também é uma prática recomendada testar se todas as portas são abertas executando a ferramenta de [avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) regularmente. Você pode saber mais sobre a funcionalidade desta ferramenta na próxima seção.

No caso de um servidor proxy sendo implantado, recomendamos que você ignore o servidor proxy para todos os serviços do teams. Embora o uso de um proxy possa funcionar, é muito provável que a qualidade seja reduzida porque a mídia está sendo forçada a usar TCP em vez de UDP. Para obter mais informações sobre servidores proxy e ignorar, consulte [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Considerações de rede adicionais

### <a name="external-name-resolution"></a>Resolução de nomes externos

Verifique se todos os computadores cliente que executam o cliente do teams podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365.

### <a name="nat-pool-size"></a>Tamanho do pool NAT

Quando vários usuários e dispositivos acessam o Office 365 usando a conversão de endereços de rede (NAT) ou a conversão de endereços de porta (PAT), você precisa garantir que os dispositivos ocultos atrás de cada endereço IP roteável publicamente não ultrapassem o número compatível.

Para reduzir esse risco, certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para evitar a exaustão de portabilidade. A exaustão da porta fará com que usuários finais e dispositivos internos tenham problemas quando se conectar aos serviços do Office 365. Para obter mais informações, consulte [suporte a NAT com o Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Orientação de detecção e prevenção de invasões

Se o seu ambiente tem um sistema de detecção de intrusão e/ou sistema de prevenção de intrusão implantado para obter uma camada adicional de segurança para conexões de saída, certifique-se de que qualquer tráfego que tenha URLs do Office 365 como seu destino seja da lista branca.

## <a name="test-the-network"></a>Testar a rede

Depois de concluir o planejamento e a preparação da rede, incluindo a atualização da largura de banda e a abertura de portas no firewall, você deve testar o desempenho da sua rede. Os resultados desse teste vão pintar uma imagem mais clara de qualquer otimização de rede ou correção necessária para o sucesso da implementação de suas equipes.

Você pode baixar a [ferramenta de avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está pronta para o Teams. A ferramenta oferece funcionalidade dupla: pode testar se todas as portas corretas foram abertas e pode testar os deficiências da rede.

Depois de baixar e instalar a ferramenta, você pode encontrá-la em C:\Program Files (x86) \Microsoft Skype for Business Network Assessment Tool. Um guia detalhado sobre como usar a ferramenta, Usage. docx, está incluído nesse diretório.

### <a name="test-for-opened-ports"></a>Testar portas abertas

Abra uma janela do prompt de comando e navegue até o diretório da ferramenta de avaliação de rede digitando **CD C:\Program Files (x86) \Microsoft Skype for Business Network Assessment Tool**. No prompt de comando, inicie o teste para portas abertas digitando **networkassessmenttool. exe/connectivitycheck**

Depois de executar as verificações, a ferramenta exibirá a mensagem "verificações concluídas com sucesso" ou relatório sobre as portas bloqueadas. Ele também gera um arquivo chamado Connectivity_results. txt, que contém a saída da ferramenta e a armazena no\\diretório da ferramenta\\\\\\ de avaliação de rede do Microsoft Skype for Business,% USERPROFILE% AppData local.

Recomendamos que você execute as verificações de conectividade regularmente para garantir que as portas tenham sido abertas e estejam funcionando corretamente.

### <a name="test-for-network-impairments"></a>Testar os deficiências da rede

Para aumentar a satisfação do usuário, você deve limitar qualquer deficiência na sua rede. Os deficiências de rede mais comuns são atrasos (latência), perda de pacote e Tremulação:

- **Latência:** Esse é o tempo necessário para obter um pacote IP do ponto a ao ponto B na rede. Esse atraso de propagação de rede é essencialmente associado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional tomada pelos vários roteadores entre eles. A latência é medida como um tempo de ida e volta.

- **Perda de pacote**: geralmente é definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes pequenos e perdidos individuais, com quase nenhum impacto nas perdas de intermitência back-to-back que fazem com que o áudio seja recortado completamente.

- **Tremulação da chegada do pacote ou simplesmente tremulação:** Esta é a alteração média no atraso entre pacotes sucessivos. O software VoIP mais moderno, incluindo o Skype for Business, pode se adaptar a alguns níveis de tremulação por meio do buffer. Isso ocorre apenas quando a tremulação excede o buffer que um participante perceberá os efeitos de tremulação.

Os valores máximos para esses problemas são descritos em [qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Ao testar esses deficiências, distinguimos entre dois segmentos separados:

- O *segmento de borda* é o segmento no qual o roteador reside. Esse é o segmento de rede lógica mais próximo conectado à Internet em cada um dos seus locais. Na maioria dos casos, esse é o ponto de conexão do roteador ou, possivelmente, uma rede de perímetro (também conhecida como *DMZ*, *zona*desmilitarizada e *sub-rede filtrada*). Nenhum outro tráfego que afete dispositivos que não o roteador deve ocorrer entre este segmento e a Internet.

- O *segmento do cliente* é o segmento lógico da rede no qual seus clientes residem.

Você deve testar ambos os segmentos usando a ferramenta de avaliação de rede. Para testar o segmento, navegue até o diretório e digite **networkassessmenttool. exe** no prompt de comando. Os resultados são gravados em um arquivo chamado Results. tsv e você pode compará-los com os [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para cada segmento.

Observe que os dois segmentos devem atender aos requisitos para uma implantação de alta qualidade. Recomendamos que você execute a ferramenta várias vezes por uma hora diretamente para obter uma boa indicação do desempenho da sua rede.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correção de rede

Se os resultados dos testes de planejamento de largura de banda, teste de porta ou de requisitos de rede mostrarem que sua rede atual precisa de correção antes de implantar o Microsoft Teams, você pode fazer isso de várias maneiras:

- Para largura de banda insuficiente, atualize as conexões para que o tráfego para o Office 365 possa fluir desprejudicado.

- Para portas bloqueadas, altere as regras de firewall e teste novamente as portas.

- Para deficiências de rede, sempre execute uma análise de causa básica.

A qualidade do serviço (QoS) pode ser usada para fazer deficiências ao priorizar e separar o tráfego. Algumas organizações optam por implantar a QoS para superar problemas de largura de banda ou restringir a quantidade de tráfego fluindo. Isso não melhora a qualidade e acarretará novos problemas. Uma análise de causa básica sempre deve ser realizada quando os deficiências da rede ultrapassarem os requisitos. A QoS pode ser uma solução. Para obter mais informações, consulte [qualidade de serviço no Microsoft Teams](qos-in-teams.md).

>[!NOTE]
>Muitas redes evoluem ao longo do tempo devido a atualizações, expansões ou outros requisitos empresariais. Verifique se você tem processos operacionais em vigor para manter essas áreas como parte do planejamento do gerenciamento do serviço.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul><li>Quem será o responsável pela conclusão das avaliações de rede adequadas em todos os segmentos de rede e locais da organização?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Você pode realizar uma avaliação de rede detalhada para ajudar a garantir que sua rede esteja pronta para a implantação do Microsoft Teams. Para obter mais informações, consulte <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">avaliação de preparação de rede</a>.</li><li>Realize a correção de rede com base nos resultados da avaliação de prontidão de rede para cada segmento de rede.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Principais argumentos

Estes são os principais argumentos desta orientação. Você deve:

- Abra as portas TCP 80 e 443 de saída de clientes que usarão o Teams.

- Abra as portas UDP 3478 a 3481 de saída de clientes que usarão o Teams.

- Verifique se você tem largura de banda suficiente para implantar o Microsoft Teams completando o planejador de [rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

- Execute a [ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) e certifique-se de que atenda aos requisitos descritos em [qualidade de mídia e desempenho de conectividade de rede](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) do segmento de borda e do segmento do cliente.

## <a name="related-topics"></a>Tópicos Relacionados

[Vídeo: planejamento de rede](https://aka.ms/teams-networking)
