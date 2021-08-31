---
title: Planejar o controle de admissão de chamada Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Saiba mais sobre o controle de admissão de chamadas, que pode impedir que as chamadas ocorrem se elas não têm qualidade de mídia ruim, Skype for Business Server Enterprise Voice.
ms.openlocfilehash: b57d9f4d6a26acb33b03ab1befb9132ffebc9a20
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725960"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planejar o controle de admissão de chamada Skype for Business Server

Saiba mais sobre o controle de admissão de chamadas, que pode impedir que as chamadas ocorrem se elas não têm qualidade de mídia ruim, Skype for Business Server Enterprise Voice.

Para aplicativos baseados em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível de redes corporativas geralmente não é considerada um fator limitante em ambientes LAN. No entanto, em links WAN que interconectam sites, a largura de banda de rede pode ser limitada.

Quando o tráfego de rede sobrescreve um link WAN, mecanismos atuais, como fila, buffer e queda de pacotes, são usados para resolver o congestionamento. O tráfego extra normalmente é atrasado até que o congestionamento de rede seja facilitado ou, se necessário, o tráfego é descartado. Para o tráfego de dados convencional em tais situações, o cliente receptor pode se recuperar. No entanto, para tráfego em tempo real, como comunicações unificadas, o congestionamento de rede não pode ser resolvido dessa maneira, pois o tráfego de comunicações unificadas é sensível à latência e à perda de pacotes. O congestionamento na WAN pode resultar em uma QoE (Qualidade de Experiência) ruim para os usuários. Para tráfego em tempo real em condições congestionadas, é melhor negar chamadas do que fornecer conexões com baixa qualidade.

O controle de admissão de chamada (CAC) determina se há largura de banda de rede suficiente para estabelecer uma sessão em tempo real de qualidade aceitável. No Skype for Business Server, o CAC controla o tráfego em tempo real apenas para áudio e vídeo, mas não afeta o tráfego de dados. Se o caminho WAN padrão não tiver a largura de banda necessária, o CAC poderá tentar roteá-la por meio de um caminho da Internet ou da PSTN (rede telefônica pública comutado).

Esta seção descreve a funcionalidade de controle de admissão de chamada e explica como planejar o CAC.

> [!NOTE]
> Skype for Business Server tem três recursos avançados Enterprise Voice: controle de admissão de chamada (CAC), serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral das informações de planejamento que são comuns a todos esses três recursos, consulte [Configurações](network-settings-for-advanced-features.md)de rede para os recursos de Enterprise Voice avançados no Skype for Business Server .

O design cac no Skype for Business Server oferece quatro atributos principais:

- é simples de implantar e gerenciar, sem a necessidade de equipamentos adicionais, como roteadores especialmente configurados.

- Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. As políticas CAC são aplicadas de acordo com a localização do ponto de extremidade, não onde o usuário está hospedado.

- Além de chamadas de voz, ele pode ser aplicado a outro tráfego, como chamadas de vídeo e sessões de conferência de áudio/vídeo.

- Oferece a flexibilidade para permitir a representação de vários tipos de topologias de rede.

Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda definidos em um link WAN, a sessão é bloqueada ou (somente para chamadas de telefone) redirecionada ao PSTN.

O CAC controla o tráfego em tempo real somente para voz e vídeo. Ele não controla o tráfego de dados.

Os administradores definem políticas de CAC, que são impostas pelo Serviço de Política de Largura de Banda instalado em cada pool de Front-End. As configurações do CAC são propagadas automaticamente para todos os Skype for Business Server Servidores Front-End em sua rede.

Para chamadas que falham devido a políticas CAC, a ordem de precedência para o redirecionamento de chamada é:

1. Internet

2. PSTN

3. Caixa postal

A gravação de detalhes da chamada (CDR) captura as informações sobre chamadas que são reencaminhadas para o PSTN ou o correio de voz. O CDR não captura as informações sobre chamadas reencaminhadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.

> [!NOTE]
> Os depósitos de correio de voz não serão negados devido a restrições de largura de banda.

O Serviço de Política de Largura de Banda gera dois tipos de arquivos de log no formato de valores separados por vírgulas (CSV). O arquivo de log **falhas de verificação** captura as informações quando as solicitações de largura de banda são negadas. O arquivo de log **utilização do link** captura um instantâneo da topologia de rede e a utilização de largura de banda do link de WAN. Ambos arquivos de log podem ajudá-lo a ajustar as políticas CAC com base na utilização.

## <a name="call-admission-control-considerations"></a>Considerações sobre o Controle de Admissão de Chamada

O administrador seleciona a instalação do Serviço de Política de Largura de Banda no primeiro pool configurado no site central. Como há apenas um site central por região da rede, há apenas um Serviço de Política de Largura de Banda por região da rede, que gerencia a política de largura de banda para aquela região, os sites associados e os links para esses sites. O Serviço de Política de Largura de Banda é executado como parte dos Servidores Front-End e, portanto, a alta disponibilidade é interna nesse pool. O Serviço de Política de Largura de Banda em execução em cada Servidor Front-End é sincronizado a cada 15 segundos. Se o pool de Front-End falhar, as políticas do CAC não serão mais impostas para esse site até que o pool de Front-End e, consequentemente, o Serviço de Política de Largura de Banda se torne operacional novamente. Isso significa que todas as chamadas serão recebidas enquanto o Serviço de Política de Largura de Banda estiver inoperante. Portanto, ainda há a possibilidade de excesso de assinatura da largura de banda dos links durante esse período

O Serviço de Política de Largura de Banda fornece alta disponibilidade em um pool de Front-End; no entanto, ele não fornece redundância entre pools de Front-End. O Serviço de Política de Largura de Banda não pode fazer failover de um pool front-end para outro. Depois que o serviço para o pool de Front-End é restaurado, o Serviço de Política de Largura de Banda é retomado e pode impor verificações de política de largura de banda novamente.

### <a name="network-considerations"></a>Considerações de Rede

Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo Serviço de Política de Largura de Banda no Skype for Business Server, essa restrição não é imposta no roteador de rede (camada 2 e 3). O CAC não pode impedir que um aplicativo de dados, por exemplo, consuma toda a largura de banda de rede em um link WAN, incluindo a largura de banda reservada para áudio e vídeo pela política cac. Para proteger a largura de banda necessária em sua rede, você pode implantar um protocolo QoS (Qualidade de Serviço), como Serviços Diferenciados (DiffServ). Portanto, uma prática prática é coordenar as políticas de largura de banda do CAC que você definir com qualquer configuração de QoS que você possa implantar.

### <a name="media-and-signaling-paths-over-vpn"></a>Mídia e Sinalização de Caminhos através de VPN

Se a sua empresa oferece suporte à mídia através de VPN, verifique se tanto o fluxo de mídia e o fluxo de sinalização vão através de VPN ou ambos são roteados pela internet. Por padrão, a mídia e os fluxos de sinalização passam pelo encapsulamento VPN.

### <a name="call-admission-control-of-outside-users"></a>Controle de Admissão de Chamada de Usuários Externos

O controle de admissão de chamada não é imposto além dos limites da organização Skype for Business Server de chamada. O CAC não pode ser aplicado ao tráfego de mídia que atravessa a Internet, que não é gerenciado por Skype for Business Server. As verificações de CAC serão executadas na parte da chamada que flui pela rede corporativa se o ponto de extremidade chamado pertencer à organização e o Servidor de Borda tiver sido adicionado à configuração de rede, conforme descrito em Implantação de controle de admissão de [chamada:](../../deploy/deploy-enterprise-voice/final-checklist.md)lista de verificação final para Skype for Business Server . Se o ponto de extremidade chamado não pertencer à organização, como um usuário federado ou PIC, nenhuma verificação de política de largura de banda será executada e a chamada de saída ignorará quaisquer restrições de CAC.

### <a name="call-admission-control-of-pstn-connections"></a>Controle de Admissão de Chamada das Conexões PSTN

O controle de admissão de chamada é executável no Servidor de Mediação, independentemente de estar conectado a um IP/PBX, um gateway PSTN ou um tronco SIP. Como o Servidor de Mediação é um agente de usuário back-to-back (B2BUA), ele encerra a mídia. Ele tem dois lados de conexão: um lado conectado ao Skype for Business Server e um lado do gateway, que está conectado a gateways PSTN, IP/PBXs ou troncos SIP. Para obter detalhes sobre conexões PSTN, consulte [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

O CAC pode ser imposto em ambos os lados do Servidor de Mediação, a menos que o bypass de mídia esteja habilitado. Se o bypass de mídia estiver habilitado, o tráfego de mídia não atravessará o Servidor de Mediação, mas fluirá diretamente entre o cliente Skype for Business e o gateway. Nesse caso, o CAC não é necessário. Para obter detalhes, consulte [Plan for media bypass in Skype for Business](media-bypass.md).

A figura a seguir ilustra como o CAC é aplicado em conexões PSTN, com e sem o bypass de mídia habilitado.

**Aplicação de controle de admissão de chamada em conexões para o PSTN**

![Voice CAC Media Bypass Connection Enforcement.](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definindo seus requisitos para controle de admissão de chamada

O planejamento do CAC (serviço de controle de admissão de chamadas) requer informações detalhadas sobre a topologia da rede da empresa. Para ajudar a planejar suas políticas do serviço de controle de admissão de chamadas, execute as etapas a seguir.

1. Identifique os hubs/backbones (chamados de regiões de rede) dentro de sua rede corporativa.

2. Identifique os escritórios ou locais (chamados sites de rede) dentro de cada região de rede.

3. Determine a rota de rede entre cada par de regiões de rede.

4. Determine os limites de largura de banda para cada link WAN.

    > [!NOTE]
    > Os limites de largura de banda referem-se à grande parte da largura de banda em um link wan é alocado para Enterprise Voice e tráfego de áudio/vídeo. Quando um link WAN é descrito como "com restrição de largura de banda", o link WAN tem um limite de largura de banda menor do que o tráfego de pico esperado no link.

5. Identifique as subredes de IP que são atribuídas a cada site de rede.

Para explicar esses conceitos, vamos usar o exemplo de topologia de rede mostrado na figura a seguir.

**Exemplo de topologia para o controle de admissão de chamada**

![Exemplo de topologia de rede litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Todos os sites de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nessa figura, são mostrados apenas links WAN que têm políticas de CAC aplicadas, com limites de largura de banda. Os sites de rede de Chicago, Nova York e Detroit são mostrados dentro da região oval da América do Norte, porque eles não estão com restrições largura de banda e não exigem políticas de CAC.

Os componentes da topologia neste exemplo são explicados nas seções a seguir. Para obter detalhes sobre como essa topologia foi planejada, incluindo os limites de largura de banda, consulte [Example: Gathering requirements for call admission control in Skype for Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identifique as regiões de rede

Uma região de rede representa um backbone de rede ou um hub da rede.

Um backbone ou hub de rede é uma parte da infraestrutura de rede do computador que interconecta diferentes partes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou subredes. Um backbone pode interligar diversas redes de um pequeno local para uma área geográfica ampla. A capacidade do backbone é normalmente maior do que as redes que se conectam a ele.

Nossa topologia de exemplo tem três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede posteriormente neste tópico). Trabalhe com sua equipe de operações de rede para identificar as regiões de rede.

### <a name="associating-a-central-site-with-each-network-region"></a>Associando um site central de cada região de rede

O CAC exige que um Skype for Business Server local central seja definido para cada região de rede. O site central é selecionado com a melhor conectividade de rede e maior largura de banda para todos os outros sites nessa região de rede. O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC. A partir do exemplo anterior, a associação apropriada é exibida na tabela a seguir.

> [!NOTE]
> Os sites centrais não correspondem necessariamente aos sites de rede. Nos exemplos nesta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham os mesmos nomes que os sites de rede. No entanto, mesmo que um site central e um site de rede compartilhem o mesmo nome, o site central é um elemento da topologia Skype for Business Server, enquanto o site de rede faz parte da rede geral na qual a topologia Skype for Business Server reside.

**Regiões de rede, sites centrais e sites de rede**

|**Região de rede**|**Central Site**|**Sites de rede**|
|:-----|:-----|:-----|
|América do Norte  <br/> |Chicago  <br/> |Chicago  <br/> Nova York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Colonia  <br/> |
|APAC  <br/> |Pequim  <br/> |Pequim  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identifique os sites de rede

Um site de rede representa um local onde a sua organização tem um espaço físico, por exemplo, um escritórios, um conjunto de edifícios ou um campus. Um espaço físico com uma LAN e conectividade WAN para outros sites é considerado um site de rede. Comece fazendo um inventário de todos os escritórios da sua organização. Em nosso exemplo de topologia, a região de rede da América do Norte consiste nos seguintes sites de rede: Nova York, Chicago, Detroit, Portland, Reno e Albuquerque.

Você deve associar cada site de rede a uma região de rede. Dependendo se o site de rede tem um link WAN restrito, uma política de largura de banda é associada ao site de rede. Para obter detalhes sobre políticas de CAC e a largura de banda que você alocar ao usá-las, consulte "Defina as políticas de largura de banda", posteriormente neste tópico. Para configurar o CAC, você deve associar os sites de rede às regiões de rede e criar políticas de alocação de largura de banda para aplicar às conexões de largura de banda restrita entre um determinado site ou região e conexões WAN entre locais e regiões.

### <a name="identify-network-links"></a>Identifique os links de rede

Os links de rede as representam conexões WAN físicas que vinculam sites e regiões diferentes. Em nosso exemplo de topologia, há dois links de rede regionais, cinco links de rede entre locais e regiões e um link de rede entre dois sites.

Os dois links regionais estão entre América do Norte e EMEA, representado como NA-EMEA-LINK, e entre APAC e EMEA, representado como EMEA-APAC-LINK.

Os links de site são indicados por linhas que conectam Portland, Reno e Albuquerque à região da América do Norte, Manila à região APAC e Colônia à região EMEA. A linha entre Reno e Albuquerque mostra um link de rede direta entre esses dois sites.

### <a name="define-bandwidth-policies"></a>Defina as políticas de largura de banda

Trabalhe com sua equipe de operações de rede para determinar a quantidade de largura de banda WAN que está disponível para o tráfego de vídeo e áudio em tempo real entre os links WAN na organização. As políticas de largura de banda são geralmente aplicadas aos links WAN quando o uso de largura de banda é restrito, isso é, espera-se que ele seja maior do que a largura de banda que pode ser alocada para as modalidades de áudio e vídeo.

CAC bandwidth policies define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.

As políticas de largura de banda do CAC podem definir o seguinte:

- Largura de banda total máxima alocada para áudio.

- Largura de banda total máxima alocada para vídeo.

- Largura de banda máxima alocada para uma única chamada de áudio (sessão).

- Largura de banda máxima alocada para uma única chamada de vídeo (sessão).

> [!NOTE]
> Todos os valores de largura de banda do CAC representam os limites máximos de largura de *banda unidirecional.*

> [!NOTE]
> Os Skype for Business Server de Política de Voz fornecem a capacidade de substituir verificações de política de largura de banda para chamadas de entrada para o usuário (não para chamadas de saída que são feitas pelo usuário). Depois da sessão ser estabelecida, o consumo de largura de banda será contabilizado com precisão. Essa configuração deve ser usada com moderação. Para obter detalhes, consulte Create or modify a voice policy and [configure PSTN](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) usage records in Skype for Business or [Modify a Voice Policy and Configure PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records) na documentação de implantação.

Para otimizar a utilização de largura de banda com base por sessão, considere o tipo de codec de áudio e vídeo que será usado. Mais especificamente, evite alocar menos largura de banda para um codec que você espera que seja usado com frequência. Por outro lado, se você deseja impedir que a mídia use um codec que exija mais largura de banda, deverá definir a largura de banda máxima por sessão menor o suficiente para desencorajar tal uso. Para o áudio, nem todos os codecs estão disponíveis para cada cenário. Por exemplo:

- Chamadas de áudio ponto a ponto entre Skype for Business pontos de extremidade usarão RTAudio (8kHz) ou RTAudio (16kHz) quando você fatorar a largura de banda e a priorização de codecs.

- As chamadas de conferência Skype for Business pontos de extremidade e o serviço de Conferência A/V usarão G.722 ou Siren.

- As chamadas para a PSTN (rede telefônica pública comutado) para ou Skype for Business pontos de extremidade usarão G.711 ou RTAudio (8kHz).

Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.

**Utilização de largura de banda por codecs**

|**Codec**|**Requisito de largura de banda sem nenhuma FEC (correção de erro antecipada)**|**Requisito de largura de banda com FEC (correção de erro antecipada)**|
|:-----|:-----|:-----|
|RTAudio (8 kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16 kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |Não aplicável  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |Não aplicável  <br/> |

> [!NOTE]
> Os requisitos de largura de banda consideram a sobrecarga de conta para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo rea) e SRTP (protoco de controle de transporte em tempo real). Eles também incluem 10 kbps para sobrecarga RTCP.

Os codecs G.722.1 e Siren são semelhantes, mas oferecem diferentes taxas de bits.

G.722, o codec padrão para Skype for Business Server conferência, é completamente diferente dos codecs G.722.1 e Siren.

O codec Siren é usado Skype for Business Server nas seguintes situações:

- Quando a política de largura de banda está definida para que o G.722 seja usado.

- Se um cliente do Communications Server 2007 ou do Communications Server 2007 R2 se conectar a um serviço de Skype for Business Server de conferência (porque esses clientes não suportam o codec G.722).

**Utilização de largura de banda por cenário**

|**Cenário**|**Requisito de largura de banda otimizado por quantidade (kbps)**|**Requisito de largura de banda para modo balanceado (kbps)**|**Requisito de largura de banda otimizado por qualidade (kbps)**|
|:-----|:-----|:-----|:-----|
|Chamadas de áudio ponto a ponto  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Chamadas em conferência  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Chamadas PSTN (entre Skype for Business e gateway PSTN, com bypass de mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN (entre Skype for Business e Servidor de Mediação, sem bypass de mídia)  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN (entre Servidor de Mediação e gateway PSTN, sem bypass de mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype for Business - Chamadas polycom  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas para cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho é significantemente simplificado.

Em nosso exemplo, o site de Nova York na região da América do Norte é atribuído às seguintes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Vamos supor que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, o computador obterá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.

> [!CAUTION]
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder o formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um Skype for Business cliente pega seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comprar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará corretamente, mesmo se você configurar sub-redes virtuais.) Por exemplo, se um cliente entrar em um computador com um endereço IP 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, Skype for Business solicitará a ID de bypass associada à sub-rede 172.29.81.0. Se a subrede é definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira sub-redes exatamente como fornecida pelos clientes Skype for Business (que são provisionadas com sub-redes durante a configuração de rede, tanto estaticamente quanto por DHCP.)

## <a name="best-practices-for-call-admission-control"></a>Práticas recomendadas para controle de admissão de chamada

Para aprimorar o desempenho e facilitar a implantação, aplique as práticas recomendadas a seguir quando implantar o controle de admissão de chamadas:

- Garanta que as WANs estejam adequadamente provisionadas para o tráfego de mídia atual e antecipado.

    > [!NOTE]
    > É recomendável que você leve em consideração um buffer para seus limites de largura de banda. Existem cenários como condições de corrida que afetam a largura de banda total usada e podem resultar em situações em que o limite da largura de banda é excedido. Por exemplo, se duas chamadas tentarem iniciar enquanto o tráfego de mídia está alcançando um limite da largura de banda, uma delas pode ser recusada porque a outra conseguiu iniciar primeiro.

- Monitore o uso da rede e registros de detalhes de chamadas para que possa escolher configurações de CAC ótimas e atualizá-las conforme o uso da rede muda.

- Use políticas de largura de banda de CAC para complementar as configurações de QoS.

- Se você desejar rerotear chamadas bloqueadas para o PSTN, verifique a funcionalidade e a capacidade do PSTN. Para detalhes, consulte [Planning Outbound Call Routing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-outbound-voice-routing).

    > [!NOTE]
    > A capacidade refere-se ao número de portas que precisam ser abertas para oferecer suporte a um possível reroteamento do PSTN.