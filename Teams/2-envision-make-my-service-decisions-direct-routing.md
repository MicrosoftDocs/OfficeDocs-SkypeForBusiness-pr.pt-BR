---
title: Tomar decisões de serviço de Roteamento Direto do Sistema de Telefonia – Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Saiba mais sobre o roteamento direto, o licenciamento e as decisões que precisam ser feitas.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57b3c8950f7e1618f578862290e8fb1696b6bc0
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018774"
---
# <a name="make-my-service-decisions"></a>Fazer minhas decisões de serviço

Para planejar a implementação técnica do roteamento direto do sistema de telefonia ("roteamento direto"), você deve fazer uma série de decisões de serviço com antecedência para preparar melhor sua organização para implementar uma solução que atenda às necessidades de negócios que você definiu.

## <a name="calling-in-teams"></a>Chamadas no Teams

Com o Microsoft Teams, os usuários podem fazer e receber chamadas telefônicas de ou para a rede telefônica pública comutada (PSTN). Seus usuários podem usar seus próprios números de telefone dedicados para fazer e receber chamadas telefônicas internacionais e nacionais (incluindo correio de voz) do aplicativo de cliente do teams.

## <a name="direct-routing"></a>Roteamento Direto

Para que os usuários do Team possam fazer e receber chamadas PSTN, eles precisam estar habilitados para o sistema telefônico, um recurso do Office 365.

Para habilitar a conectividade com a PSTN, você pode usar o roteamento direto para dar às pessoas em sua organização a capacidade de fazer e receber chamadas telefônicas fora da organização pela PSTN.

Com o roteamento direto, a conectividade PSTN é facilitada por um provedor de terceiros, permitindo que você continue usando os troncos PSTN existentes fornecidos pelo provedor de serviços PSTN. Isso permite a implantação em países em que o sistema telefônico com planos de chamada ("planos de chamada") não está disponível ou em implantações em que um contrato de provedor de serviços PSTN existente precisa ser mantido ou a interoperabilidade com certos sistemas locais é Necessário.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilidade de roteamento direto

O roteamento direto está disponível em qualquer país onde o Office 365 está disponível. Veja a [disponibilidade internacional](https://products.office.com/business/international-availability) para obter uma lista desses países.

Depois de confirmar que a sua organização pode obter o recurso do sistema de telefonia, Compile a lista de locais de usuários ou escritórios em que você implementará o sistema telefônico com base na lista de países e regiões disponíveis. Identifique também os usuários para os quais você vai habilitar os planos de chamada ou roteamento direto para cada local que você tiver.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Identifique os locais do usuário ou os escritórios nos quais você implementará o sistema telefônico.<li>Identifique os usuários para os quais você vai habilitar os planos de chamada ou roteamento direto para cada local que você tiver.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios a serem habilitados para o sistema telefônico.<li>Documentar a lista de usuários para os quais você vai habilitar planos de chamada ou roteamento direto para cada local que você tiver</ul>|

> [!TIP]
> Veja a seguir um exemplo de uma lista de habilitação de site de roteamento direto.
> 
> | **Office**                     | **Local**   | **Serviço do sistema telefônico** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Austrália      | Serviço PSTN herdado |
> | 100 Alma Road             | Hong Kong SAR  | Roteamento Direto do Sistema Telefônico |
> | One Marina Boulevard           | Cingapura      | Roteamento Direto do Sistema Telefônico |
> | 32 London Bridge Street        | Reino Unido | Sistema telefônico com planos de chamada |
> | 39 quai du Président Roosevelt | França         | Sistema telefônico com planos de chamada |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

O sistema telefônico exige que todos os usuários da sua organização tenham um número de telefone exclusivo para discagem direta (DID) do Direct Inward. Com o roteamento direto, os números de telefone e os serviços de emergência são fornecidos pelo seu provedor de serviços PSTN.

> [!NOTE]
> Com o roteamento direto, os usuários podem continuar usando seus próprios números de telefone, fornecidos pelo provedor de serviços PSTN.
> 
> [!TIP]
> Você pode usar o modelo a seguir para documentar os detalhes dos números de telefone.
> 
> |Usuário |Número de telefone |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Lahr de Louis | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Caixa postal

O correio de voz na nuvem, da plataforma de correio de voz do Azure, oferece suporte a depósitos de correio de voz para trocar caixas de correio somente e não é compatível com sistemas de email

O correio de voz na nuvem inclui a transcrição de correio de voz, que é habilitada para todos os usuários da sua organização por padrão. Suas necessidades comerciais podem exigir que você desabilite a transcrição de correio de voz para usuários específicos ou todos em toda a organização. Se sua organização decidir manter a transcrição de correio de voz habilitada, você também precisará considerar se a máscara de obscenidades da transcrição de correio de voz precisa estar habilitada. Para obter mais detalhes, consulte [definindo políticas de correio de voz em sua organização](set-up-phone-system-voicemail.md) .

Para obter mais informações sobre o correio de voz em uma implementação de sistema telefônico, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você habilitará o correio de voz na nuvem na sua implementação de roteamento direto.<li>Decida se você habilitará ou desabilitará a transcrição de correio de voz e o mascaramento de obscenidades da transcrição de correio de voz em toda a organização ou para usuários específicos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Se aplicável, documente os pontos de decisão para dar suporte ao correio de voz na nuvem.<li>Se você habilitar ou desabilitar o correio de voz, a transcrição de correio de voz e o mascaramento de obscenidades da transcrição de correio de voz somente para usuários específicos, documente a lista de usuários.</ul>|

> [!TIP]
> Detalhes do correio de voz na nuvem para a implementação de planos de chamada podem ser documentados na tabela a seguir.
> 
> | **Usuário**         | **Caixa de correio do Exchange** | **Habilitar correio de voz?** | **Transcrição do correio de voz** | **Máscara de obscenidade de transcrição de correio de voz** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Sim                   | Habilitado                     | Habilitado                                       |
> | Lidia Holloway   | Online               | Sim                   | Habilitado                     | Desabilitado                                      |
> | Lahr de Louis       | Local          | Sim                   | Habilitado                     | Habilitado                                       |
> | Marcel Beauchamp | Local          | Sim                   | Desabilitado                    | N/D                                           |
> | Rachelle Cormier | Online               | Sim                   | Desabilitado                    | N/D                                           |
> | Isabell Potvin   | Local          | Sim                   | Desabilitado                    | N/D                                           |
> 
> [!NOTE]
> Para usar o Microsoft Teams e o correio de voz, os usuários devem ter caixas de correio do Exchange. Veja [como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para obter mais detalhes.

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Licenciamento para roteamento direto

Se a sua organização pretende usar o roteamento direto, você precisará obter as licenças necessárias. Os usuários de roteamento direto devem ter as seguintes licenças atribuídas no Office 365:

-   Sistema telefônico da Microsoft

-   Microsoft Teams

-   Audioconferência

A licença de conferência de áudio é necessária para adicionar participantes externos a reuniões agendadas, seja discando para elas ou fornecendo o número de discagem. Quando um participante externo é discada, o serviço de audioconferência faz a chamada usando recursos de chamada online. A licença de audioconferência é opcional e só é necessária para os usuários que organizam conferências de equipes que incluem videoconferências.


> [!NOTE]
> Para fornecer números de telefone de chamada de conferência gratuita e para dar suporte à discagem de conferência discada para números de telefone internacionais, você deve configurar [créditos de comunicações](what-are-communications-credits.md) para a sua organização.

A conferência de áudio e o sistema telefônico podem ser licenciados separadamente como serviços complementares para clientes existentes que tenham planos de assinatura do Office 365 E3 ou E1; Eles já estão incluídos como parte do plano de assinatura do Office 365 e5.

> [!TIP]
> Você também pode usar o roteamento direto para os usuários que estão habilitados para chamar planos ao rotear suas chamadas para PBXs de terceiros. Para obter mais detalhes, consulte [Licenciamento e outros requisitos de roteamento direto](direct-routing-plan.md#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se a sua organização não tiver a licença do sistema de telefonia necessária, decida se você adquirirá a licença do sistema de telefone, faça o acompanhamento de suas assinaturas existentes do Office 365 ou da aquisição do serviço de complemento do sistema telefônico.<li>Decida se você precisará de créditos de comunicações para a sua implementação de roteamento direto.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os grupos de divisão, departamento, escritório ou usuário para os quais você atribuirá uma licença do sistema de telefonia.<li>Se a conferência de áudio com números de chamada gratuita estiver em escopo, documente os grupos de divisão, departamento, escritório ou usuário você habilitará os créditos de comunicações.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Considerações sobre o Office 365

Qualquer usuário que será habilitado para roteamento direto deve ser hospedado no Office 365. Para implantações híbridas com o Skype for Business Server ou Lync Server local, você precisa mover os usuários para o Skype for Business Online antes de configurá-los para usar o roteamento direto com o Teams.

Todos os usuários que estão no escopo de implementações de roteamento direto devem ser habilitados para Teams.

Seu locatário do Office 365 deve ser habilitado com um ou mais domínios, porque o \*domínio default. onmicrosoft.com não pode ser usado com roteamento direto. Para obter mais informações sobre domínios e locatários do Office 365, consulte [perguntas frequentes sobre domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se algum usuário precisa ser migrado para o Skype for Business online para dar suporte ao roteamento direto.<li>Identifique os usuários que precisam estar habilitados para o Teams.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar a lista de usuários que precisam se mover para o Skype for Business Online e estar habilitados para equipes.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Considerações de SBC

Você precisa usar controladores de borda de sessão certificados e com suporte (SBCs) que precisem ser emparelhados ao serviço de roteamento direto para fornecer conectividade PSTN para seus usuários. Para obter uma lista de SBCs certificados, consulte [controladores de borda de sessão com suporte](direct-routing-plan.md#supported-session-border-controllers-sbcs).

Dependendo do seu ambiente, do número de locais e dos requisitos de roteamento de voz, talvez seja necessário implantar vários SBCs para dar suporte à sua base de usuários.

### <a name="sbc-domain-names"></a>Nomes de domínio SBC

Cada SBC que você emparelhar com roteamento direto deve ter um nome DNS exclusivo. Os nomes DNS do SBC devem ser de um dos nomes de domínio registrados no locatário do Office 365. Se o seu locatário tiver sido atribuído a vários nomes de domínio, você poderá usar qualquer um desses nomes de domínio ao planejar os nomes DNS dos seus SBCs.

> [!IMPORTANT]
> O uso de *. onmicrosoft.com para o nome DNS do SBC não é permitido.

### <a name="certificates"></a>Certificados

Cada SBC implantado com roteamento direto exige um certificado obtido de uma lista de autoridades de certificação com suporte. O certificado deve incluir o nome DNS do SBC nos campos assunto, nome alternativo do assunto ou nome comum.

> [!NOTE]
> Também há suporte para o uso de certificados curinga com SBCs.

Para obter mais informações e uma lista de autoridades de certificação com suporte, consulte [certificado público confiável para o SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Endereços IP e portas SBC

Cada SBC deve ser configurado usando um endereço IP público acessível a partir de datacenters do Office 365. Você também pode configurar a NAT (conversão de endereços de rede) para publicar seu SBCs em datacenters do Office 365.

SBCs exige conectividade bidirecional para se comunicar com os serviços de nuvem para sinalização e mídia. A sinalização é manipulada pelo componente denominado *proxy SIP*, e a mídia é manipulada pelos *processadores de mídia*.

Você precisa definir números de porta específicos em cada SBC para sinalização e mídia SIP e configurar seus firewalls para permitir o tráfego bidirecional para essas portas e seus endereços IP associados.

Para obter mais detalhes, consulte [sinalização SIP: FQDNs](direct-routing-plan.md#sip-signaling-fqdns) e [tráfego de mídia: intervalos de porta](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> É altamente recomendável definir um limite máximo de sessões simultâneas para cada SBC, com base no modelo SBC. Esse limite, então, dispararia uma notificação quando o SBC estiver sendo executado em ou perto de sua capacidade.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida em quais locais você implantará o SBCs.<li>Escolha um nome DNS para cada SBC que você pretende implantar.<li>Com base na decisão do nome do domínio SBC, decida se você usará um certificado curinga para dar suporte a todos os SBCs na sua implantação ou a um certificado exclusivo por SBC.<li>Decida de qual autoridade de certificação pública você obterá os certificados para seu SBCs.<li>Defina um par de endereços IP públicos/porta para cada SBC que você irá implantar e decida se irá atribuir os endereços IP públicos ao SBCs ou usar o NAT.<li>Identifique o número máximo de sessões simultâneas que cada SBC suporta ou pode manipular.<li>Determine qual SBCs será configurado usando bypass de mídia.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente cada decisão sendo feita para o SBCs usando a tabela de exemplo a seguir.</ul>|


> [!TIP]
> Use o modelo a seguir para documentar os detalhes do SBC para a sua implantação de roteamento direto.
> 
> | **Nome DNS (FQDN) do SBC** | **Marca e modelo de SBC** | **Certificado** | **Local**  | **Endereço IP** | **Porta de sinalização SIP** | **ADDRESS?** | **Máximo de sessões simultâneas** | **Bypass de mídia habilitado?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | A ser determinado | \*. contoso.com | Amsterdã | A ser determinado | A ser determinado | Sim | A ser determinado | Não |
> | SBC-Asia.contoso.com | A ser determinado | \*. contoso.com | Hong Kong SAR | A ser determinado | A ser determinado | Não | A ser determinado | Sim |
> | SBC-Africa.contoso.com | A ser determinado | \*. contoso.com | Joanesburgo | A ser determinado | A ser determinado | Sim | A ser determinado | Sim |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Roteamento de voz

Você precisa configurar o sistema de telefonia da Microsoft para direcionar as chamadas para o SBCs específico para roteamento direto. Você pode configurar as rotas de voz com base em:

-   Padrão de número chamado.

-   Padrão de número chamado + o usuário que faz a chamada.


O encaminhamento de chamadas é composto pelos seguintes elementos:

-   Política de roteamento de voz – contêiner para usos de PSTN; pode ser atribuído a um usuário ou a vários usuários

-   Usos de PSTN – contêiner para roteiros de voz e usos de PSTN; pode ser compartilhado em diferentes políticas de roteamento de voz

-   Rotas de voz – padrão de número e conjunto de gateways PSTN online a serem usados para chamadas em que o número de chamada corresponda ao padrão

-   Gateway PSTN online-ponteiro em SBC, também armazena a configuração que é aplicada quando uma chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (PAI) ou codecs preferenciais; pode ser adicionado a roteiros de voz

Você pode configurar as rotas de voz com roteamento direto para coexistir com planos de chamada. Essa configuração permite que os planos de chamadas encaminhe algumas das chamadas para o SBCs específico usando o roteamento direto.

> [!TIP]
> A SBCs pode ser designada como *ativa* e de *backup*. Isso significa que, quando o SBC que está configurado como ativo para este padrão de número (ou padrão de número + usuário específico) não estiver disponível, as chamadas serão roteadas para um SBC de backup.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Escolha as políticas de roteamento de voz, os usos de PSTN e as rotas de voz que você criará para dar suporte a locais de usuários ou escritórios em escopo para a implementação de roteamento direto.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Políticas de roteamento de voz do documento, usos de PSTN e rotas de voz para sua organização.<li>Documente os usuários a serem atribuídos para cada política de roteamento de voz que você definir.</ul>|

> [!TIP]
> Use o modelo a seguir para documentar as políticas de voz para a sua implantação de roteamento direto.
> 
> | **Uso de PSTN** | **Rota de voz** | **Padrão de número** | **Prioridade** | **SBC** | **Descrição** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Somente EUA | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX |
> | Somente EUA | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX |
> | Somente EUA | "Outro + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Rota para qualquer padrão de número |
> 
> [!IMPORTANT]
> Os usos de PSTN nas políticas de roteamento de voz são aplicados em ordem e, se for encontrada uma correspondência na primeira utilização, outros usos nunca serão avaliados.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Políticas de chamadas e de interoperabilidade

O roteamento direto só tem suporte no Microsoft Teams. Para fazer ou receber chamadas PSTN por meio do direcionamento direto, você precisa configurar as políticas necessárias para garantir que as chamadas recebidas sejam recebidas no Microsoft Teams.

> [!NOTE]
> Os usuários habilitados para roteamento direto não podem fazer ou receber chamadas de roteamento direto usando o Skype for Business e, portanto, devem ser implantados no cliente da equipe.

Você pode configurar seus usuários para definir o Microsoft Teams como cliente preferencial para chamadas por um dos dois métodos a seguir:

-   Configurar o usuário para o modo somente para equipes

-   Configure o Microsoft Teams como o cliente de chamadas preferenciais atribuindo o TeamsCallingPolicy e o TeamsInteropPolicy.

Para obter mais detalhes, consulte [atribuir o modo apenas Teams para usuários para garantir chamadas no Microsoft Teams](direct-routing-configure.md#assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida qual abordagem você usará para definir o Microsoft Teams como o cliente preferencial para chamadas.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os usuários a serem configurados com políticas de interoperabilidade e chamadas.</ul>|

> [!IMPORTANT]
> Quando um usuário estiver configurado para o modo somente Teams, este usuário não poderá mais se conectar ao Skype for Business.

Para que os usuários vejam a guia chamadas no cliente do Teams, você precisa habilitar a chamada particular em um nível organizacional para o locatário. Consulte [habilitar chamadas para o Microsoft Teams](direct-routing-configure.md) para obter mais detalhes sobre como habilitar chamadas privadas.


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisões de serviço de documento

Use as informações das seções anteriores deste artigo para documentar suas decisões de serviço. Em geral, esta documentação conterá as seguintes seções principais:

-   Sistema telefônico com planos de chamada lista de habilitação de sites

-   Detalhes da configuração do correio de voz

-   Atribuição de licença para usuários de roteamento direto do sistema telefônico

-   Detalhes da configuração do SBC

-   Política de roteamento de voz e detalhes de roteamento

-   Detalhes da política de chamada e interoperabilidade

<!--ENDOFSECTION-->
