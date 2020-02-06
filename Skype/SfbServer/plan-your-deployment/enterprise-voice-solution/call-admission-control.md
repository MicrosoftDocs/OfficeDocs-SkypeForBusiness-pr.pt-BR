---
title: Planejar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Saiba mais sobre o controle de admissão de chamadas, que pode impedir que chamadas sejam feitas se tivessem uma qualidade de mídia ruim no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 33aad955d0d1c592900683213a13e50433265a10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803231"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planejar o controle de admissão de chamadas no Skype for Business Server

Saiba mais sobre o controle de admissão de chamadas, que pode impedir que chamadas sejam feitas se tivessem uma qualidade de mídia ruim no Skype for Business Server Enterprise Voice.

Para aplicativos baseados em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível das redes empresariais geralmente não é considerada um fator limitante nos ambientes de LAN. Entretanto, nos links WAN que interconectam locais, a largura de banda de rede pode ser limitada.

Quando o tráfego de rede sobrecarrega um link WAN, mecanismos atuais, como enfileiramento, armazenamento em buffer e remoção de pacotes são usados para resolver o congestionamento. O tráfego extra é normalmente atrasado até que o congestionamento de rede melhore ou, se necessário, o tráfego seja removido. No caso de tráfego de dados convencional nessas situações, o cliente receptor pode se recuperar. Entretanto, para o tráfego em tempo real, como comunicações unificadas, o congestionamento da rede não pode ser resolvido dessa maneira, uma vez que o tráfego das comunicações unificadas é sensível à latência e à perda de pacotes. O congestionamento na WAN pode resultar em uma QoE (Qualidade da Experiência) ruim para os usuários finais. Para o tráfego em tempo real em condições congestionadas, é melhor negar as chamadas do que permitir conexões com qualidade ruim.

O controle de admissão de chamadas (CAC) determina se há largura de banda de rede suficiente para estabelecer uma sessão de tempo real de qualidade aceitável. No Skype for Business Server, o CAC controla o tráfego em tempo real somente para áudio e vídeo, mas não afeta o tráfego de dados. Se o caminho de WAN padrão não tiver a largura de banda necessária, o CAC pode tentar direcionar a chamada por meio de um caminho da Internet ou da rede telefônica pública comutada (PSTN).

Esta seção descreve a funcionalidade de controle de admissão de chamadas e explica como planejar o CAC.

> [!NOTE]
> O Skype for Business Server tem três recursos avançados de voz empresarial: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral do planejamento de informações comuns a todos esses três recursos, consulte [configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server](network-settings-for-advanced-features.md).

O design do CAC no Skype for Business Server oferece quatro atributos principais:

- É simples implantar e gerenciar sem exigir equipamento adicional, como roteadores especialmente configurados.

- Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. Políticas do CAC são impostas de acordo com o local em que o ponto de extremidade está localizado, não onde o usuário está hospedado.

- Além de chamadas de voz, ela pode ser aplicada a outro tráfego, como chamadas com vídeo e sessões de videoconferência/videoconferência.

- Fornece a flexibilidade para habilitar a representação de vários tipos de topologias de rede.

Se uma nova sessão de voz ou de vídeo exceder os limites de largura de banda definidos em um link de rede de longa distância, a sessão será bloqueada ou (apenas para chamadas telefônicas) redirecionada para a PSTN.

O CAC controla o tráfego em tempo real para voz e vídeo somente. Ele não controla o tráfego de dados.

Os administradores definem políticas do CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de front-ends. As configurações de CAC são automaticamente propagadas para todos os servidores front-end do Skype for Business Server na sua rede.

Para chamadas que falham devido às políticas do CAC, a ordem de precedência para redirecionar a chamada é a seguinte:

1. Internet

2. PSTN

3. Caixa postal

A gravação de detalhes de chamadas (CDR) captura informações sobre chamadas redirecionadas para a PSTN ou para a caixa postal. A CDR não captura informações sobre chamadas redirecionadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.

> [!NOTE]
> Os depósitos da caixa postal não serão negados devido a restrições de largura de banda.

O serviço de política de largura de banda gera dois tipos de arquivos de log no formato CSV (valores separados por vírgula). O arquivo de log de **falhas de verificação** captura informações quando as solicitações de largura de banda são negadas. O arquivo de log de **utilização do link** captura um instantâneo da topologia de rede e a utilização da largura de banda do link WAN. Esses dois arquivos de registro podem ajudá-lo a ajustar suas políticas do CAC com base na utilização.

## <a name="call-admission-control-considerations"></a>Considerações sobre o controle de admissão de chamadas

O administrador seleciona a instalação do serviço de política de largura de banda no primeiro pool configurado no site central. Como há um único site central por região de rede, há apenas um serviço de política de largura de banda por região de rede, que gerencia a política de largura de banda para essa região, seus sites associados e os links para esses sites. O serviço de política de largura de banda é executado como parte dos servidores front-end e, portanto, a alta disponibilidade é interna dentro desse pool. O serviço de política de largura de banda executado em cada servidor front-end sincroniza a cada 15 segundos. Se o pool de front-ends falhar, as políticas do CAC não serão mais impostas para esse site até o pool de front-ends e, consequentemente, o serviço de política de largura de banda ficará operacional novamente. Isso indica que todas as chamadas passarão durante a duração em que o serviço de política de largura de banda está fora do serviço. Portanto, há a possibilidade de largura de banda superassinatura de seus links durante este período

O serviço de política de largura de banda fornece alta disponibilidade em um pool de front-end; no entanto, ele não fornece redundância entre pools de front-end. O serviço de política de largura de banda não pode fazer failover de um pool de front-end para outro. Uma vez que o serviço para o pool de front-end seja restaurado, o serviço de política de largura de banda é retomado e pode impor verificações de política de largura

### <a name="network-considerations"></a>Considerações de rede

Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo serviço de política de largura de banda no Skype for Business Server, essa restrição não é imposta no roteador de rede (camada 2 e 3). O CAC não pode impedir um aplicativo de dados, por exemplo, de consumir toda a largura de banda de rede em um link de WAN, incluindo a largura de banda reservada para áudio e vídeo por meio da sua política do CAC. Para proteger a largura de banda necessária na sua rede, você pode implantar um protocolo de QoS (qualidade de serviço), como serviços diferenciados (DiffServ). Portanto, uma prática recomendada é coordenar as políticas de largura de banda do CAC que você define com qualquer configuração de QoS que possa ser implantada.

### <a name="media-and-signaling-paths-over-vpn"></a>Caminhos de mídia e sinalização via VPN

Se a sua empresa for compatível com mídia via VPN, certifique-se de que tanto o fluxo de mídia quanto o fluxo de sinalização passem pela VPN ou ambos sejam roteados pela Internet. Por padrão, a mídia e os fluxos de sinalização passam pelo túnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Controle de admissão de chamadas de usuários externos

O controle de admissão de chamadas não é aplicado além dos limites da organização do Skype for Business Server. Não é possível aplicar o CAC ao tráfego de mídia que atravessa a Internet, o que não é gerenciado pelo Skype for Business Server. Cheques do CAC serão executados na parte da chamada que flui pela rede da empresa se o ponto de extremidade chamado pertence à organização, e o servidor de borda foi adicionado à configuração de rede, conforme descrito em [implantação de controle de admissão de chamadas: lista de verificação final do Skype for Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Se o ponto de extremidade chamado não pertence à organização, como um usuário federado ou PIC, nenhuma verificação de política de largura de banda será executada e a chamada de saída ignorará as restrições do CAC.

### <a name="call-admission-control-of-pstn-connections"></a>Controle de admissão de chamadas de conexões PSTN

O controle de admissão de chamadas é aplicável no servidor de mediação independentemente de estar conectado a um IP/PBX, a um gateway PSTN ou a um tronco SIP. Como o servidor de mediação é um agente de usuário back-to-back (B2BUA), ele termina a mídia. Ele tem dois lados de conexão: um lado conectado ao Skype for Business Server e um lado do gateway, que é conectado a gateways PSTN, IP/PBXs ou troncos SIP. Para obter detalhes sobre conexões PSTN, consulte [planejar a conectividade PSTN no Skype for Business Server](pstn-connectivity-0.md).

O CAC pode ser imposto em ambos os lados do servidor de mediação, a menos que a opção ignorar mídia esteja habilitada. Se a bypass de mídia estiver habilitada, o tráfego de mídia não percorrerá o servidor de mediação, mas fluirá diretamente entre o cliente Skype for Business e o gateway. Nesse caso, o CAC não é necessário. Para obter detalhes, consulte [plano de bypass de mídia no Skype for Business](media-bypass.md).

A figura a seguir ilustra como o CAC é imposto sobre conexões PSTN com e sem o bypass de mídia habilitado.

**Aplicação de controle de admissão de chamadas em conexões com PSTN**

![Aplicação de voz do CAC ignorando a imposição de conexão](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definindo seus requisitos para o controle de admissão de chamadas

O planejamento de controle de admissão de chamadas (CAC) requer informações detalhadas sobre a topologia de rede corporativa. Para ajudar a planejar suas políticas de controle de admissão de chamadas, siga estas etapas.

1. Identifique os hubs/backbones (chamados de regiões de rede) dentro da sua rede corporativa.

2. Identifique os escritórios ou locais (chamados de sites de rede) em cada região de rede.

3. Determine a rota de rede entre todos os pares de regiões de rede.

4. Determine os limites de largura de banda para cada link de WAN.

    > [!NOTE]
    > Os limites de largura de banda referem-se à quantidade de largura de banda de um link de WAN atribuída ao tráfego de voz e áudio/vídeo da empresa. Quando um link de WAN é descrito como "largura de banda restringida", o link de WAN tem um limite de largura de banda menor do que o tráfego de pico esperado no link.

5. Identifique as sub-redes IP atribuídas a cada site de rede.

Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.

**Exemplo de topologia para controle de admissão de chamadas**

![Litware Inc. exemplo de topologia de rede](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Todos os sites de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nesta figura, somente links WAN que têm políticas de CAC aplicadas são mostrados, com limites de largura de banda. Os sites de rede de Chicago, Nova York e Detroit são exibidos dentro da elipse da América do Norte, pois eles não são restringidos por largura de banda e, portanto, não exigem políticas do CAC.

Os componentes deste exemplo de topologia são explicados nas seções a seguir. Para obter detalhes sobre como essa topologia era planejada, incluindo os limites de largura de banda, consulte [exemplo: coletando requisitos para controle de admissão de chamadas no Skype for Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identificar regiões de rede

Uma região de rede representa um backbone de rede ou um hub de rede.

Um backbone ou Hub de rede é uma parte da infraestrutura de rede de computador que interconecta partes diferentes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou sub-redes. Um backbone pode unir várias redes diferentes de um local pequeno para uma ampla área geográfica. A capacidade do backbone normalmente é maior do que a das redes conectadas a ele.

Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede mais adiante neste tópico). Trabalhe com sua equipe de operações de rede para identificar suas regiões de rede.

### <a name="associating-a-central-site-with-each-network-region"></a>Associando um site central a cada região de rede

O CAC requer que um site central do Skype for Business Server seja definido para cada região de rede. O site central é selecionado com a melhor conectividade de rede e largura de banda mais alta para todos os outros sites na região da rede. O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC. No exemplo anterior, a associação apropriada é mostrada na tabela a seguir.

> [!NOTE]
> Os sites centrais não correspondem necessariamente a sites de rede. Nos exemplos desta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham o mesmo nome dos sites de rede. No entanto, mesmo se um site central e um site de rede compartilharem o mesmo nome, o site central será um elemento da topologia do Skype for Business Server, enquanto o site de rede faz parte da rede geral na qual a topologia do Skype for Business Server reside.

**Regiões de rede, sites centrais e sites de rede**

|**Região de rede**|**Site central**|**Sites de rede**|
|:-----|:-----|:-----|
|América do Norte  <br/> |Chicago  <br/> |Chicago  <br/> Nova York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Cologne  <br/> |
|APAC  <br/> |Pequim  <br/> |Pequim  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identificar sites de rede

Um site de rede representa um local onde sua organização tem um local físico, por exemplo, escritórios, um conjunto de prédios ou um campus. Um local físico com uma LAN e com conectividade de WAN a outros sites é considerado um site de rede. Comece inventariando todos os escritórios da sua organização. Na nossa topologia de exemplo, a região de rede da América do Norte consiste nos seguintes sites de rede: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

Você deve associar todos os sites de rede a uma região de rede. Dependendo se o site de rede tem um link de WAN restrito, uma política de largura de banda é associada ao site de rede. Para obter detalhes sobre as políticas do CAC e a largura de banda que você atribuir usando-as, consulte "definir políticas de largura de banda" mais adiante neste tópico. Para configurar o CAC, associe sites de rede com regiões de rede e, em seguida, crie políticas de alocação de largura de banda para aplicar às conexões restritas de largura de banda entre um determinado site ou região e as conexões WAN entre os sites e regiões.

### <a name="identify-network-links"></a>Identificar links de rede

Links de rede representam conexões para a WAN física que vincula diferentes áreas e sites. Na nossa topologia de exemplo, há dois links de rede regionais, cinco links de rede entre regiões e sites e um link de rede entre dois sites.

Os dois links regionais estão entre a América do Norte e a EMEA, representados como NA-EMEA-LINK e entre a Ásia e a EMEA, representados como EMEA-Ásia-LINK.

Os links de site são indicados pelas linhas que conectam a Portland, Reno e Albuquerque à região da América do Norte, Manila à região da Ásia e Cologne à região da EMEA. A linha entre Reno e Albuquerque mostra um link de rede direto entre esses dois sites.

### <a name="define-bandwidth-policies"></a>Definir políticas de largura de banda

Trabalhe com sua equipe de operações de rede para determinar Quanta largura de banda de WAN está disponível para tráfego de áudio e vídeo em tempo real nos links WAN de sua organização. Geralmente, as políticas de largura de banda são aplicadas ao WAN links se o uso da largura de banda for restrito; ou seja, se ela deveria ser maior que a largura de banda que pode ser alocada para modalidades de áudio e vídeo.

Políticas de largura de banda do CAC definem a largura de banda máxima que pode ser reservada para modalidades de áudio e vídeo em tempo real. Como o CAC não limita a largura de banda de outro tráfego, ele não pode evitar outros tráfegos de dados, como uma transferência de arquivo grande, fluxo de música, desde o uso de toda a largura de banda da rede.

As políticas de largura de banda do CAC podem definir qualquer um dos seguintes itens:

- Largura de banda total máxima atribuída para áudio.

- Largura de banda total máxima alocada para vídeo.

- Largura de banda máxima alocada para uma única chamada de áudio (sessão).

- Largura de banda máxima alocada para uma única chamada de vídeo (sessão).

> [!NOTE]
> Todos os valores de largura de banda do CAC representam os limites de largura de banda *unidirecionais*

> [!NOTE]
> Os recursos da política de voz do Skype for Business Server fornecem a capacidade de substituir verificações de política de largura de banda para chamadas recebidas para o usuário (não para chamadas feitas pelo usuário). Depois que a sessão for estabelecida, o consumo de largura de banda será considerado com precisão. Esta configuração deve ser usada com moderação. Para obter detalhes, consulte [criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) ou [modificar uma política de voz e configurar registros de uso PSTN](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) na documentação de implantação.

Para otimizar a utilização da largura de banda com base em cada sessão, considere o tipo de codecs de áudio e vídeo que será usado. Em particular, evite alocar largura de banda insuficiente para um codec que você espera que seja usado com frequência. Por outro lado, se você quiser impedir que a mídia use um codec que exija mais largura de banda, deve definir a largura de banda máxima por sessão, o suficiente para desencorajar tal uso. Para áudio, nem todos os codecs estão disponíveis para todos os cenários. Por exemplo:

- As chamadas de áudio ponto a ponto entre os pontos de extremidade do Skype for Business usarão o RTAudio (8kHz) ou o RTAudio (16kHz) quando você fatorar a largura de banda e a priorização de codecs.

- As chamadas em conferência entre os pontos de extremidade do Skype for Business e o serviço de conferência A/V usarão G. 722 ou sirene.

- As chamadas para a rede telefônica pública comutada (PSTN) para ou dos pontos de extremidade do Skype for Business usarão G. 711 ou RTAudio (8kHz).

Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.

**Utilização de largura de banda por codecs**

|**Codec**|**Requisitos de largura de banda sem correção de erro antecipado (FEC)**|**Requisitos de largura de banda com a correção de erro antecipada (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |Não aplicável  <br/> |
|RTVideo (VGA de 30 fps)  <br/> |610 kbps  <br/> |Não aplicável  <br/> |

> [!NOTE]
> Os requisitos de largura de banda levam em conta a sobrecarga para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo real) e SRTP (Secure real-time Transport Protocol). Eles também incluem 10 kbps para a sobrecarga RTCP.

Os codecs G. 722.1 e sirene são semelhantes, mas oferecem tarifas de bit diferentes.

O G. 722, o codec padrão da conferência do Skype for Business Server, é completamente diferente dos codecs G. 722.1 e sirene.

O codec sirene é usado no Skype for Business Server nas seguintes situações:

- Se a política de largura de banda estiver definida como muito baixa para G. 722 a ser usada.

- Se um cliente do Communications Server 2007 ou Communications Server 2007 R2 se conectar a um serviço de conferência do Skype for Business Server (pois esses clientes não dão suporte para o codec G. 722).

**Utilização da largura de banda por cenário**

|**Cenário**|**Requisitos de largura de banda otimizados para quantidade (Kbps)**|**Requisitos de largura de banda para o modo balanceado (Kbps)**|**Requisitos de largura de banda otimizados para qualidade (Kbps)**|
|:-----|:-----|:-----|:-----|
|Chamadas de áudio ponto a ponto  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Chamadas em conferência  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Chamadas PSTN (entre o Skype for Business e o gateway PSTN com bypass de mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN (entre o Skype for Business e o servidor de mediação, sem bypass de mídia)  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chamadas PSTN (entre o servidor de mediação e o gateway PSTN sem bypass de mídia)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype para empresas-chamadas Polycom  <br/> |101 kbps  <br/> |101 kbps  <br/> |101 kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com o administrador da rede para determinar quais sub-redes IP serão atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.

Em nosso exemplo, o site de Nova York na região da América do Norte recebe as seguintes sub-redes de IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que o Bob geralmente funcione no Detroit, vá para o escritório de Nova York para treinamento. Quando ele ligar o computador e se conectar à rede, o computador receberá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.

> [!CAUTION]
> As sub-redes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato fornecido pelos computadores cliente para serem usadas corretamente para o bypass de mídia. Um cliente Skype for Business leva seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar a ID de bypass associada a cada cliente, o registrador irá comparar a lista de sub-redes IP associadas a cada site de rede em relação à sub-rede fornecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamadas, mas não o bypass de mídia, o controle de admissão de chamadas funcionará corretamente mesmo se você configurar sub-redes virtuais.) Por exemplo, se um cliente entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede de IP de 255.255.255.0, o Skype for Business solicitará o bypass ID associado ao subnet 172.29.81.0. Se a subrede for definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador entre em sub-redes exatamente como é fornecido pelos clientes do Skype for Business (provisionados com sub-redes durante a configuração de rede, de forma estática ou por DHCP.)

## <a name="best-practices-for-call-admission-control"></a>Práticas recomendadas para controle de admissão de chamada

Para melhorar o desempenho e facilitar a implantação, aplique as seguintes práticas recomendadas ao implantar o controle de admissão de chamadas:

- Garanta que as WANs sejam provisionadas de forma adequada para tráfego de mídia atual e previsto.

    > [!NOTE]
    > Recomendamos que você Fatore em um buffer para seus limites de largura de banda. Há cenários como condições de corrida que afetam a largura de banda total usada e podem resultar em situações em que o limite de largura de banda é excedido. Por exemplo, se duas chamadas tentam iniciar enquanto o tráfego de mídia está se aproximando de um limite de largura de banda, um deles pode ser negado porque o outro gerenciado para iniciar primeiro.

- Monitorar o uso da rede e os registros de detalhes da chamada para que você possa escolher as configurações de CAC otimizadas e atualizar as configurações de CAC como alterações de uso de rede.

- Use as políticas de largura de banda do CAC para complementar as configurações de QoS.

- Se você quiser redirecionar chamadas bloqueadas para a PSTN, verifique a funcionalidade e a funcionalidade da PSTN. Para obter detalhes, consulte [planejando o roteamento de chamadas de saída](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > A capacidade se refere ao número de portas que você precisa abrir para dar suporte a redirecionamento PSTN potencial.


