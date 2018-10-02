---
title: Configurar para live eventos no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Conheça as etapas para configurar ao vivo para eventos no Microsoft Teams, incluindo Otimize sua rede, como atribuir licenças, habilitando o agendamento para usuários e configurando um provedor de eCDN de evento ao vivo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354360"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar para live eventos no Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Quando você estiver configurando para eventos ao vivo, há diversas etapas que devem ser executadas:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Etapa 1: Configurar sua rede para live eventos no Microsoft Teams
Os eventos de início rápido ao vivo exigem que você preparar [a rede da sua organização para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
Verifique se você tem as atribuições de licença correta para [quem pode criar e agendar eventos ao vivo?](#who-can-create-and-schedule-live-events) e [quem pode assistir eventos ao vivo?](#who-can-watch-live-events).

## <a name="step-3-enable-live-event-scheduling-for-users"></a>Etapa 3: Habilitar o agendamento de evento ao vivo para usuários
Evento ao vivo agendamento é habilitado por padrão para os usuários de equipes, mas se você estiver buscando os usuários agendem eventos externos codificador há etapas adicionais que você deve fazer.

### <a name="for-quick-start-events"></a>Eventos de início rápido
Use a configuração *AllowBroadcastScheduling* no **TeamsMeetingBroadcastPolicy** no PowerShell equipes para controlar se o usuário pode criar eventos ao vivo em equipes ou não. Saiba mais sobre como gerenciar TeamsMeetingBroadcastPolicy [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Se você ainda não atribuída uma política personalizada atribuída aos usuários, os usuários receberá a política *Global* , que tem a gravação habilitada por padrão.

Verifique se o parâmetro *AllowBroadcastScheduling* estiver definido como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Atribua o usuário para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a>Cenários de usuário
**Você deseja todos os usuários da sua empresa, possam criar eventos ao vivo.**

Se os usuários são atribuídos a política *Glocal* , execute e confirme que *AllowBroadcastScheduling* * estiver definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se os usuários recebem uma política que não seja a política *Global* , execute o seguinte e verificar se a opção *-AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Você desejar que o evento ao vivo planejamento ser desabilitado de 100% em sua organização.**

Desabilitar o agendamento de transmissão, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Atribua a todos os usuários em sua organização para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Você deseja que um grande número de usuários possam criar eventos ao vivo, mas deseja impedir que um conjunto de usuários criá-los.**

Atribuir a política *Global* usando o **Grant-CsTeamsMeetingBroadcastPolicy** para alguns dos usuários (que você deseja enabled), mas primeiro execute o seguinte e verificar se *AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Atribua um ou mais usuários à política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crie e atribua uma diretiva para desabilitar o agendamento usando o cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** para os outros usuários (serem desabilitadas). 

Criar a nova diretiva com ele desabilitada, execute:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Desabilitar o agendamento, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Você deseja eventos ao vivo devem ser desabilitados para um grande número de usuários, mas deseja permitir que um conjunto de usuários para criá-los.**

Desabilitar o agendamento de transmissão, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Em seguida, atribua esses usuários para a política *Global* , execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Criar e atribuir uma política para habilitar o agendamento, execute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilite o agendamento, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a>Para eventos externos codificador
Você deve fazer o seguinte procedimento para habilitar o agendamento para os usuários de evento ao vivo.

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Etapa 1: Habilitar o Microsoft Stream para usuários em sua organização * *
Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo. Para obter mais detalhes, consulte [Visão geral do licenciamento de Stream](https://docs.microsoft.com/stream/license-overview) .

> ! [NOTA] Microsoft Stream não está incluído nos planos Business Essentials ou Business Premium.  

Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream. Certifique-se de que Microsoft Stream não é bloqueado para os usuários conforme definido [neste](https://docs.microsoft.com/stream/disable-user-organization)artigo.

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Etapa 2: Verifique se os usuários têm permissão de criação de evento ao vivo na Microsoft Stream * *
Por padrão, os administradores podem criar codificador externa a eventos ao vivo. Administrador do Microsoft Stream pode [Permitir que usuários adicionais para criação de evento ao vivo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) no fluxo.  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Etapa 3: Verifique se o evento ao vivo organizadores tem consentiu a política da empresa definida pelo fluxo admin * *
Se um administrador do Microsoft Stream [definir uma política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar conteúdo, em seguida, os usuários devem fazer isso antes de criar um evento ao vivo (com a produção de codificador externo) em equipes. Antes da distribuição o recurso de eventos ao vivo na organização, certifique-se de tem consentiu usuários que criarão esses eventos ao vivo a política. 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Etapa 4: Configurar o provedor de eCDN para live eventos no Microsoft Teams 
Reprodução de vídeos do evento ao vivo usa a taxa de bits adaptável streaming (ABR), mas é um fluxo de unicast, que significa que cada visualizador está recebendo o seu próprio fluxo de vídeo da internet. Para eventos ao vivo ou vídeos enviados para grandes partes da sua organização, pode haver uma quantidade significativa de largura de banda de internet consumida por visualizadores. Para organizações que desejam reduzir esse tráfego da internet para eventos ao vivo, eventos ao vivo soluções integradas da Microsoft confiam definidos de parceiros de entrega de vídeo oferecem software redes (SDNs) ou redes de fornecimento de conteúdo corporativo (eCDNs). Esses SDN eCDN plataformas permitem que as organizações a otimizar a largura de banda de rede sem prejudicar o usuário final experiências de exibição. Nossos parceiros podem ajudar a habilitar uma distribuição mais flexível e eficiente de vídeo em sua rede corporativa.

**Compra & instalação sua solução fora do Microsoft Teams** Obtenha ajuda especializada com o dimensionamento de entrega de vídeo aproveitando parceiros de entrega confiável de vídeo da Microsoft. Para poder habilitar um provedor de entrega de vídeo ser usado com equipes, você deve adquirir e a solução SDN/eCDN externamente e separada das equipes de instalação.

As seguintes soluções SDN/eCDN previamente são integradas e podem ser configurado para ser usado com o Microsoft Stream.

- **Hive Streaming** fornece uma solução simple e eficiente para distribuição de vídeo da empresa ao vivo e sob demanda. Hive é uma solução baseada em software que não exige nenhum hardware adicional ou a largura de banda e fornece uma maneira segura para habilitar milhares de visualizadores de vídeos simultâneos sem afetar a sua rede. Para clientes que desejem para entender que o vídeo do impacto está tendo em sua rede antes da compra de uma solução SDN/eCDN, Hive Streaming também fornece uma solução de análise baseada em navegador para os clientes da Microsoft. [Saiba mais](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** é uma baseada na nuvem inteligente aos distribuição plataforma, que aproveita a infra-estrutura de rede existente para entregar conteúdo, em vários formulários, (live streaming de vídeo, vídeo sob demanda, atualizações de software, patches de segurança, etc.) com mais rapidamente e confiável e com menos largura de banda. Nossa plataforma segura é confiável por maiores instituições financeiras de todo o mundo e sem hardware adicional, são fáceis de instalação e manutenção. [Saiba mais](http://www.kollective.com).
 
- **Conheça OmniCache** fornece a distribuição de rede de última geração e garante perfeito fornecimento de conteúdo de vídeo entre WANs globais, ajudando produtores de evento otimizar a largura de banda de rede e suporte difusões bem-sucedida evento ao vivo e sob demanda Streaming. O suporte para OmniCache conheça para eventos ao vivo do início rápido estarão disponíveis em breve.  [Saiba mais](http://www.ramp.com). 
 
> [!NOTE] 
> Sua solução eCDN escolhida está sujeito selecionado de **termos do provedor de terceiros 3º da política de privacidade e de serviço**, quais rege o uso da solução do provedor eCDN. O uso da solução do provedor eCDN não estará sujeito a termos de licenciamento de volume do Microsoft ou termos de serviços Online. Se não concordar com os **termos do provedor de terceiros 3º**, não habilite a solução eCDN em equipes. 

**Configurar um eCDN para "Quick start" eventos ao vivo** Você pode configurar o provedor de eCDN para eventos ao vivo em equipes usando o PowerShell. 

> [!NOTE] 
> Um provedor de eCDN único pode ser configurado para sua organização. 

***Hive*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. Primeiro, obtenha a URL do modelo ID e a API de licença de seu contato Hive, em seguida, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Você pode usar o cmdlet [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) do PowerShell para configurar o provedor de eCDN. Primeiro obter o token de API e a URL do modelo de API do seu contato Kollective, depois, execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Configurar um eCDN para eventos de "Codificador externo" ao vivo** 

Se você planeja criar eventos ao vivo que usam codificadores externos, você precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching) também. 

## <a name="next-steps"></a>Próximos passos
Vá para [equipes Confgure live eventos](configure-teams-live-events.md).
