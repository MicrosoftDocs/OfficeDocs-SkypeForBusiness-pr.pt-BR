---
title: Tomar decisões de serviço de roteamento direto de sistema do telefone - Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 07/09/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Saiba mais sobre roteamento direto, licenciamento, e as decisões que precisam ser realizadas.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf52071419b3ee9bb606649d6fa50870e23879cc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23869457"
---
# <a name="make-my-service-decisions"></a>Tomar decisões meu serviço

Para planejar a implementação técnica do sistema direto roteamento de telefone ("direto roteamento"), você deve fazer uma série de decisões de serviço antes do tempo para melhor preparar sua organização para implementar uma solução que atenda aos requisitos de negócios que você definiu.

## <a name="calling-in-teams"></a>Fazendo chamadas no Microsoft Teams

Com Teams da Microsoft, os usuários podem fazer ou receber chamadas telefônicas para ou da rede telefônica pública comutada (PSTN). Seus usuários podem usar seus próprios números de telefone dedicado para fazer e receber chamadas de telefone nacionais e internacionais (incluindo caixa postal) do aplicativo cliente equipes.

## <a name="direct-routing"></a>Direcionar circulação

Para usuários de equipes poder fazer e receber chamadas PSTN, elas precisam ser habilitados para o sistema telefônico, um recurso do Office 365.

Para habilitar a conectividade à PSTN, você pode usar o roteamento direto para atribuir às pessoas na sua organização a capacidade de fazer e receber chamadas telefônicas fora da organização no PSTN.

Com o roteamento direto, conectividade PSTN é facilitada por um provedor de terceiros, permitindo que você continuar a usar seus troncos PSTN existentes, fornecidos pelo provedor de serviços PSTN. Isso permite a implantação em países onde o sistema telefônico com chamar planos ("chamar planos") não estão disponíveis ou em implantações onde um contrato de provedor de serviço PSTN existente que precisam ser mantidas ou interoperabilidade com sistemas determinados local é Necessário.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilidade de roteamento direto

Roteamento direto está disponível em qualquer país em que o Office 365 está disponível. Consulte [disponibilidade internacional](https://products.office.com/business/international-availability) para obter uma lista esses países.

Depois de confirmar que sua organização pode obter o recurso de sistema telefônico, compile a lista de locais do usuário ou de onde você vai implementando sistema telefônico, com base na lista de países disponíveis e regiões de escritórios. Também identificam os usuários que você pretende habilitar roteamento direto ou em planos de chamada para cada local que você tenha.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Identifique os locais do usuário ou escritórios na qual você implementará o sistema telefônico.<li>Identifique os usuários que você pretende habilitar roteamento direto ou em planos de chamada para cada local que você tenha.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os locais do usuário ou escritórios estar habilitado para o sistema telefônico.<li>A lista de usuários que você pretende habilitar roteamento direto ou em planos de chamada para cada local que você tenha de documentos</ul>|

> [!TIP]
> Abaixo é um exemplo de uma lista de habilitação do site de roteamento direto.
> | **Escritório**                     | **Local**   | **Serviço de sistema telefônico** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Austrália      | Serviço PSTN herdado |
> | 100 Alma Road             | Hong Kong SAR  | Roteamento direto de sistema do telefone |
> | One Marina Boulevard           | Cingapura      | Roteamento direto de sistema do telefone |
> | 32 London Bridge Street        | Reino Unido | Sistema de Telefonia com Planos de Chamadas |
> | 39 quai du Président Roosevelt | França         | Sistema de Telefonia com Planos de Chamadas |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Sistema telefônico exige que cada usuário na sua organização tenha um inward direto exclusivo discando o número de telefone (DID). Com o roteamento direto, os números de telefone e os serviços de emergências são fornecidos pelo provedor de serviços PSTN.

> [!NOTE]
> Com o roteamento direto, os usuários possam continuar usando seus próprios números de telefone fornecidos pelo provedor de serviços PSTN.

> [!TIP]
> Você pode usar o modelo a seguir para documentar os detalhes de números de telefone.
>|Usuário |Número de telefone |
>|-----|-------------|
>|Emily Braun | + 44 23 4567 8901 |
>|Lidia Holloway | + 44 23 4567 89112 |
>|Louis Lahr | + 44 23 4567 8921 |
>|Marcel Beauchamp | TBA |
>|Rachelle Cormier | TBA |
>|Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Caixa postal

Caixa postal de sistema telefônico, possibilitada pela serviços de caixa postal do Azure, suporta depósitos de correio de voz em somente caixas postais do Exchange e não oferece suporte a sistemas de email de terceiros.

A caixa postal do Sistema de Telefonia inclui transcrição da caixa postal que, por padrão, está habilitada para todos os usuários da organização. Suas necessidades de negócios podem exigir que você desative as transcrições de caixa postal para usuários específicos ou todos em toda a organização. Se a sua organização decidir manter a transcrição do correio de voz habilitada, você precisa considerar também se mascaramento de obscenidades transcrição caixa postal precisa estar habilitado. Consulte [definir políticas de caixa postal na sua organização](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) para obter mais detalhes.

Para obter mais informações sobre a caixa postal na implementação de um sistema telefônico, consulte [Configure a caixa postal do sistema telefônico](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você habilitará o sistema telefônico de caixa postal na sua implementação de roteamento direto.<li>Decida se vai habilitar ou desabilitar a transcrição do correio de voz e caixa postal mascaramento de obscenidades transcrição em toda a organização ou usuários específicos.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Se aplicável, documente os pontos de decisão para oferecer suporte à caixa postal do sistema telefônico.<li>Se você vai habilitar ou desabilitar a caixa postal, transcrições de caixa postal e caixa postal mascaramento de obscenidades transcrição somente para usuários específicos, essa lista de usuários do documento.</ul>|

> [!TIP]
> Detalhes de caixa postal de sistema de telefone para a implementação de planos de chamada podem ser documentados como na tabela a seguir.
> | **Usuário**         | **Caixa de correio do Exchange** | **Habilitar a caixa postal?** | **Transcrição do correio de voz** | **Mascaramento de obscenidades de transcrição de caixa postal** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Sim                   | Habilitado                     | Habilitado                                       |
> | Lidia Holloway   | Online               | Sim                   | Habilitado                     | Desabilitado                                      |
> | Louis Lahr       | No local          | Sim                   | Habilitado                     | Habilitado                                       |
> | Marcel Beauchamp | No local          | Sim                   | Desabilitado                    | N/D                                           |
> | Rachelle Cormier | Online               | Sim                   | Desabilitado                    | N/D                                           |
> | Isabell Potvin   | No local          | Sim                   | Desabilitado                    | N/D                                           |

> [!NOTE]
> Para usar as equipes e caixa postal, os usuários devem ter caixas de correio do Exchange. Para obter mais detalhes, consulte [como o Exchange e equipes da Microsoft interagir](https://docs.microsoft.com/microsoftteams/exchange-teams-interact) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Licenciamento para roteamento direto

Se sua organização pretende usar o roteamento direto, você precisa obter licenças necessárias. Usuários de roteamento direto devem ter as seguintes licenças atribuídas no Office 365:



-   Sistema telefônico da Microsoft

-   Microsoft Teams

-   Audioconferência

Licença de conferência de áudio é necessária para adicionar participantes externos para reuniões agendadas, discando a eles para acessá-los ou fornecendo o número de discagem. Quando um participante externo é discado check-out para, o serviço de conferência de áudio faz a chamada usando os recursos de chamada online. Licença de conferência de áudio é opcional e somente necessários para os usuários que vai ser organizar Teams conferências que incluem áudio da conferência.


> [!NOTE]
> Para fornecer números de telefone de ponte de conferência de discagem gratuita e para oferecer suporte a discagem de conferência aos números de telefone internacional, você deve configurar o [Communications créditos](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) para sua organização.

Conferência de áudio e sistema telefônico podem ser licenciados separadamente como serviços de complemento para os clientes existentes que têm o Office 365 E3 ou E1 planos de assinatura; eles já estão incluídos como parte do plano de assinatura do Office 365 E5.

> [!TIP]
> Você também pode usar o roteamento direto para os usuários habilitados para planos de chamada ao rotear as chamadas para PBXs de terceiros. Para obter mais detalhes, consulte [licenciamento e outros requisitos de roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se sua organização não tiver a licença de sistema telefônico necessária, decida se você vai adquirir a licença do sistema telefônico passando o backup de suas assinaturas do Office 365 existentes ou adquirindo o serviço de complemento do sistema telefônico.<li>Decida se você precisará créditos de comunicações para a implementação de roteamento direto.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os grupos de divisão, departamento, office ou usuário vai atribuir uma licença de sistema telefônico.<li>Se a conferência de áudio com números para ligações gratuitas estiver em escopo, os grupos de divisão, departamento, office ou usuário você habilitará o créditos de comunicações do documento.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Considerações sobre o Office 365

Qualquer usuário que será habilitado para roteamento direto deve ser hospedado no Office 365. Para implantações híbridas com Skype local para Business Server ou o Lync Server, você precisa mover usuários para Skype para Business Online antes de configurá-los para usar o roteamento direto com equipes.

Todos os usuários que estão no escopo de implementações de roteamento direto devem ser habilitados para equipes.

Locatário do Office 365 deve estar habilitado com um ou mais domínios, pois o padrão \*. domínio onmicrosoft.com não pode ser usado com o roteamento direto. Para obter mais informações sobre os domínios e locatários do Office 365, consulte [FAQ de domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se todos os usuários precisam ser migrados para o Skype para negócios on-line para dar suporte ao roteamento direto.<li>Identifique os usuários que precisam estar habilitadas para equipes.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>A lista de usuários que precisam mover para Skype para Business Online e ser habilitada para equipes do documento.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Considerações de SBC

Você precisará usar controladores de borda de sessão de certificados e com suporte (SBCs) que precisam ser emparelhados ao serviço de roteamento direto para fornecer conectividade PSTN para seus usuários. Para obter uma lista de certificados SBCs, consulte [Suporte para controladores de borda de sessão](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs).

Dependendo do seu ambiente, o número de locais e requisitos de roteamento de voz, você talvez seja necessário implantar vários SBCs para oferecer suporte à sua base de usuários.

### <a name="sbc-domain-names"></a>Nomes de domínio SBC

Cada SBC que você emparelhar com o roteamento direto deve ter um nome exclusivo do DNS. Os nomes de SBC DNS devem ser um dos nomes de domínio registrados no inquilino do Office 365. Se seu locatário tiver sido atribuído a vários nomes de domínio, você pode usar qualquer um desses nomes de domínio ao planejar os nomes dos seus SBCs DNS.

> [!IMPORTANT]
> O uso de *. onmicrosoft.com para o nome DNS de SBC não é permitido.

### <a name="certificates"></a>Certificados

Cada implantação SBC com o roteamento direto requer um certificado obtido de uma lista de autoridades de certificação com suporte. O certificado deve incluir o nome DNS de SBC no assunto, nome alternativo da entidade ou campos de nome comum.

> [!NOTE]
> Também há suporte para o uso de certificados curinga com SBCs.

Para obter mais informações e uma lista de autoridades de certificação com suporte, consulte o [certificado público de confiável para o SBC](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Portas e endereços IP de SBC

Cada SBC deve ser configurado por meio de um endereço IP público acessível a partir de centros de dados do Office 365. Você também pode configurar a conversão de endereço de rede (NAT) para publicar suas SBCs em centros de dados do Office 365.

SBCs exigem conectividade bidirecional para se comunicar com os serviços de nuvem para a sinalização e mídia. Sinalização é tratado pelo componente denominado *Proxy SIP*, e a mídia é manipulada pelos *Processadores de mídia*.

Você precisará definir números de porta específica em cada SBC para sinalização SIP e a mídia e configure seus firewalls para permitir que o tráfego bidirecional essas portas e seus endereços IP associados.

Para obter mais detalhes, consulte [a sinalização SIP: FQDNs e portas de firewall](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports) e [tráfego de mídia: intervalos de porta](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges).


> [!NOTE]
> É altamente recomendável definir um limite máximo de sessão simultâneas para cada SBC, com base no modelo SBC. Esse limite, em seguida, seria disparar uma notificação quando o SBC está sendo executado ou próximo sua capacidade.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida em quais locais você vai implantar SBCs.<li>Decida um nome DNS para cada SBC que você estiver planejando implantar.<li>Com base na decisão de nome de domínio SBC, decida se você vai usar um certificado curinga para dar suporte a todos os SBCs em sua implantação ou um certificado dedicado por SBC.<li>Decida qual autoridade de certificação pública você obtenha os certificados para seus SBCs de.<li>Definir um par de endereço/porta IP público para cada SBC você implantar e decidir se você irá atribuir os endereços IP públicos para os SBCs ou usar NAT.<li>Identifique o número máximo de sessões simultâneas que oferece suporte a cada SBC ou pode manipular.<li>Decida quais SBCs serão configurados por meio de Bypass de mídia.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente cada decisão sendo feita para os SBCs usando a tabela de exemplo a seguir.</ul>|


> [!TIP]
> Use o modelo a seguir para documentar os detalhes SBC para sua implantação de roteamento direto.
> | **Nome DNS de SBC (FQDN)** | **SBC e o modelo** | **Certificado** | **Local**  | **Endereço IP** | **Porta de sinalização SIP** | **NAT?** | **Sessões simultâneas do max** | **Bypass de mídia habilitado?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*. contoso.com | Amsterdã | TBD | TBD | Sim | TBD | Não |
> | SBC-Asia.contoso.com | TBD | \*. contoso.com | Hong Kong SAR (香港特別行政區) | TBD | TBD | Não | TBD | Sim |
> | SBC-Africa.contoso.com | TBD | \*. contoso.com | Joanesburgo | TBD | TBD | Sim | TBD | Sim |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Roteamento de voz

Você precisará configurar o sistema de telefone da Microsoft para rotear as chamadas para os SBCs específicos para roteamento direto. Você pode configurar rotas de voz com base em:

-   Padrão de número chamado.

-   Padrão de número chamado + do usuário que faz a chamada.


Roteamento de chamadas é composto pelos seguintes elementos:

-   Política de roteamento de voz – contêiner para usos de PSTN; podem ser atribuídas a um usuário ou a vários usuários

-   Usos da PSTN – contêiner para rotas de voz e usos de PSTN; podem ser compartilhados em diferentes políticas de roteamento de voz

-   Rotas – padrão de número e o conjunto de Gateways de PSTN Online para usar para chamadas onde o número da chamada corresponde ao padrão de voz

-   Gateway PSTN online - ponteiro de SBC, também armazena a configuração que é aplicada quando uma chamada é feita por meio de SBC, como forward P-Asserted-Identity (PAI) ou Codecs preferencial; podem ser adicionados às rotas de voz

Você pode configurar suas rotas de voz com o roteamento direto para coexistir com planos de chamada. Essa configuração permite chamar planos rotear algumas das chamadas para os SBCs específicos usando o roteamento direto.

> [!TIP]
> SBCs podem ser designados como *ativos* e de *backup*. Isso significa que, quando o SBC que está configurado como ativo para este número padrão — ou o número padrão + específica do usuário — não estiver disponível, as chamadas serão roteadas para um SBC backup.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida o roteamento diretivas, usos da PSTN e roteamentos de voz que você vai criar para locais de usuário de suporte ou escritórios em escopo para a implementação do direto roteamento de voz.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente as políticas de roteamento de voz, usos da PSTN e roteamentos de voz para sua organização.<li>Documente os usuários a ser atribuído para cada política de roteamento de voz que você define.</ul>|

> [!TIP]
> Use o modelo a seguir para documentar as políticas de voz para sua implantação de roteamento direto.
> | **Uso de PSTN** | **Rota de voz** | **Padrão de número** | **Prioridade** | **SBC** | **Descrição** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Somente nos EUA | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Roteiro ativo para números chamados +1 425 XXX XX XX ou +1 206 XXX XX XX |
> | Somente nos EUA | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Rota de backup para números chamados +1 425 XXX XX XX ou +1 206 XXX XX XX |
> | Somente nos EUA | "Outros + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Encaminhar para números chamados + 1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Rota para qualquer número padrão |

> [!IMPORTANT]
> Os usos da PSTN em políticas de roteamento de voz são aplicados na ordem, e se uma correspondência for encontrada no primeiro uso, outros usos nunca são avaliados.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Chamada e interoperabilidade políticas

Roteamento direto somente é compatível com Microsoft Teams. Para fazer ou receber chamadas PSTN por meio de roteamento direto, você precisa configurar as políticas necessárias para garantir que as chamadas recebidas são recebidas em equipes.

> [!NOTE]
> Os usuários habilitados para roteamento direto não é possível fazer ou receber direcionar chamadas de roteamento usando Skype para negócios e, portanto, deve ser implantado o cliente de equipes.

Você pode configurar os usuários para definir as equipes como seu cliente preferencial para chamadas por um dos dois métodos a seguir:

-   Configurar o usuário para o modo somente equipes

-   Configure equipes como o cliente de chamada preferencial, atribuindo o TeamsCallingPolicy e o TeamsInteropPolicy.

Para obter mais detalhes, consulte [definir equipes da Microsoft como o preferencial chamar cliente para os usuários](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida qual abordagem você usará para definir equipes como cliente preferencial para chamadas.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Os usuários a ser configurado com as políticas de interoperabilidade e chamadas do documento.</ul>|

> [!IMPORTANT]
> Quando um usuário estiver configurado para o modo somente equipes, esse usuário não é mais pode entrar no Skype para negócios.

Para que os usuários para ver a guia chamadas no cliente equipes, você precisará habilitar privada chamando-se em um nível organizacional para o inquilino. Consulte [Habilitar chamar para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams) para obter mais detalhes sobre como habilitar chamadas particulares.


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisões de serviço de documento

Use as informações das seções anteriores deste artigo para documentar suas decisões de serviço. Em geral, esta documentação irá conter as seguintes seções principais:

-   Lista de habilitação de locais do Sistema de Telefonia com Planos de Chamadas

-   Detalhes de configuração da caixa postal

-   Atribuição de licença para usuários de roteamento direto de sistema do telefone

-   Detalhes de configuração de SBC

-   Política de roteamento e detalhes de roteamento de voz

-   Detalhes da política de chamada e de interoperabilidade

<!--ENDOFSECTION-->
