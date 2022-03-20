---
title: Endereços de emergência para locais remotos
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Saiba como a Microsoft dá suporte a informações de local de envio para dar suporte a chamada de emergência.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d80854fc36e6914ba48e8993d298c75b136bd06f
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660706"
---
# <a name="emergency-addresses-for-remote-locations"></a>Endereços de emergência para locais remotos

Este artigo descreve o suporte da Microsoft para informações de local de chamada de emergência do 911 nos Estados Unidos. Esse suporte garante que as informações de local de envio mais precisas possíveis são fornecidas Teams usuários que fazem chamadas de emergência. Independentemente da localização do chamador, local ou trabalhando em casa, as informações de local do chamador enviadas para o PSAP (Ponto de Atendimento de Segurança Pública) devem ser precisas.

Este artigo inclui informações sobre a conformidade da Microsoft com a Lei ray BAUM para sistemas telefônicos de várias linhas (MLTS). A Lei ray BAUM estende os requisitos de Lei de Kari, que entraram em vigor no início de 2021. Para obter mais informações sobre a Lei de RAY BAUM e a Lei de Kari, consulte [Dispatchable Location for 911 Calls](https://www.fcc.gov/911-dispatchable-location) and [Multi-line Telephone Systems – Kari's Law and RAY BAUM's Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements). 

Os usuários que trabalham em casa agora podem definir seus próprios endereços de emergência, se aplicável. Este artigo descreve como você pode configurar políticas de usuário para que os usuários finais possam definir seus endereços de emergência.

Embora essas informações se apliquem à chamada de emergência 911 nos Estados Unidos, os locais inseridos pelo usuário também serão transmitidos para o centro de triagem no Canadá.

Este artigo contém as seguintes seções:

- [Suporte para informações de local de chamada de emergência](#support-for-emergency-calling-location-information)
- [Precedência de local](#location-precedence)
- [Classificação e roteamento de endereços de emergência](#emergency-address-classification-and-routing)
- [Permitir que os usuários finais configurem seu endereço de emergência](#enable-end-users-to-configure-their-emergency-address)
- [Observações e restrições](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Suporte para informações de local de chamada de emergência

Para dar suporte a esses requisitos, o Teams usa os serviços de localização fornecidos pelo respectivo sistema operacional para sugerir um endereço, se concedido permissão pelo administrador ou usuário. O usuário final pode confirmar o local de um endereço sugerido, editá-lo ou inserir manualmente um novo. Um endereço confirmado, editado ou inserido manualmente é salvo no cliente Teams para que o endereço confirmado pelo usuário seja usado automaticamente quando o cliente estiver conectado a essa rede. Os endereços salvos pelo usuário são automaticamente limpos quando o Teams cliente é assinado.


## <a name="location-precedence"></a>Precedência de local

Os endereços de emergência Teams podem ser categorizados por tipos diferentes. A lista a seguir mostra a precedência de local usada quando um número de emergência é discado:

1. Um endereço adquirido dinamicamente definido pelo locatário administrar no Serviço de Informações de Local.

2. Um endereço ao qual o usuário final foi confirmado, editado ou inserido manualmente, que está associado à rede local à qual o cliente Teams está conectado.

3. Um endereço sugerido automaticamente pelo sistema operacional.

4. Um endereço que o administrador atribui estaticamente ao usuário.


## <a name="emergency-address-classification-and-routing"></a>Classificação e roteamento de endereços de emergência

A tabela a seguir mostra os tipos de endereços de emergência e os métodos de roteamento associados para cada tipo: se a chamada é roteada automaticamente para o PSAP de serviço ou triagem para precisão antes de transferir para o PSAP de serviço. Esse comportamento de roteamento é suportado nos Estados Unidos para todos os usuários do Plano de Chamadas, operadores Conexão parceiros e provedores de serviço de chamadas de emergência certificados de Roteamento Direto.


| Tipo de endereço de emergência | Método de roteamento de emergência |
| :------------| :-------|
| Endereço de emergência adquirido dinamicamente definido pelo administrador. | Direct to PSAP. |
| Endereço de emergência obtido do sistema operacional sem **confirmação de precisão** pelo usuário. | Exibido e transferido para pSAP. |
| Endereço de emergência obtido do sistema operacional **com confirmação de precisão** pelo usuário.| Direct to PSAP. |
| Endereço de emergência obtido do sistema operacional e editado e confirmado pelo usuário. | Exibido e transferido para pSAP. |
| Endereço de emergência inserido e confirmado pelo usuário. | Exibido e transferido para pSAP. |
| Endereço de emergência atribuído estaticamente ao usuário/número. | Exibido e transferido para pSAP. |
| Null | Exibido e transferido para pSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permitir que os usuários finais configurem seu endereço de emergência

Para habilitar esse recurso para os usuários finais, use o cmdlet New-CsTeamsEmergencyCallingPolicy PowerShell e de definir o parâmetro ExternalLocationLookupMode como Habilitado. Veja o exemplo a seguir: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Depois de habilitar esse recurso para os usuários finais, na guia Chamadas, o usuário pode adicionar, editar ou confirmar um endereço de emergência e exibir o endereço depois que ele for definido. Para obter mais informações sobre como os usuários finais podem definir serviços de localização, consulte [Work from Home Emergency 911: enable location services](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

No Windows, você pode gerenciar o serviço de Windows local e se os aplicativos têm acesso ao local, usando a política de grupo ou usando o gerenciamento de dispositivo móvel [(MDM)](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation).

Para obter mais informações sobre Windows local, [consulte Windows local e privacidade](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Observações e restrições

Considere o seguinte:

- A experiência work-from-home descrita é para Teams desktop em Windows e Mac.

- Teams telefones não suportam a experiência work-from-home.

- Teams mobile oferece suporte à detecção automática de localização, mas não à experiência inserida pelo usuário descrita.

- As configurações de privacidade podem estar em conflito com a detecção automática de localização - os sistemas de Gerenciamento de Dispositivo Móvel podem ser usados.


## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)

- [Work from Home Emergency 911: enable location services](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

