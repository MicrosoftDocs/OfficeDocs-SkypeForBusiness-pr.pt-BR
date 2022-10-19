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
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Saiba como a Microsoft dá suporte a informações de localização expedidas para dar suporte a chamadas de emergência.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d7fd3111991c4a2e5e0d16e5d46aba411b1553c3
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584575"
---
# <a name="emergency-addresses-for-remote-locations"></a>Endereços de emergência para locais remotos

Este artigo descreve o suporte da Microsoft para informações de local de chamada de emergência 911 no Estados Unidos. Esse suporte garante que as informações de localização expedidas mais precisas possíveis são fornecidas para os usuários do Teams que fazem chamadas de emergência. Independentemente da localização do chamador , no local ou trabalhando em casa, as informações de localização de um chamador enviadas para o PSAP (Ponto de Atendimento à Segurança Pública) devem ser precisas.

Este artigo inclui informações sobre a conformidade da Microsoft com o MLTS (Ray BAUM's Act for Multi Line Telephone Systems). A Lei ray BAUM estende os requisitos da Lei de Kari, que entraram em vigor no início de 2021. Para obter mais informações sobre a Lei de RAY BAUM e a Lei de Kari, consulte Local Despedível para [chamadas 911](https://www.fcc.gov/911-dispatchable-location) e sistemas telefônicos de várias linhas [– Lei de Kari e Ray BAUM Lei 911 Direct Discling, Notificação e](https://www.fcc.gov/mlts-911-requirements) Requisitos de Localização Expedicionável. 

Os usuários que trabalham em casa agora podem definir seus próprios endereços de emergência, se aplicável. Este artigo descreve como você pode configurar políticas de usuário para que os usuários finais possam definir seus endereços de emergência.

Embora essas informações se apliquem à chamada de emergência 911 no Estados Unidos, os locais inseridos pelo usuário também serão transmitidos para o centro de triagem no Canadá.

Este artigo contém as seguintes seções:

- [Suporte para informações de local de chamada de emergência](#support-for-emergency-calling-location-information)
- [Precedência de local](#location-precedence)
- [Classificação e roteamento de endereços de emergência](#emergency-address-classification-and-routing)
- [Permitir que os usuários finais configurem seu endereço de emergência](#enable-end-users-to-configure-their-emergency-address)
- [Observações e restrições](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Suporte para informações de local de chamada de emergência

Para dar suporte a esses requisitos, o Teams usa os serviços de localização fornecidos pelo respectivo sistema operacional para sugerir um endereço, se for concedida permissão pelo administrador ou usuário. O usuário final pode confirmar o local de um endereço sugerido, editá-lo ou inserir um novo manualmente. Um endereço confirmado, editado ou inserido manualmente é salvo no cliente do Teams para que o endereço confirmado pelo usuário seja usado automaticamente quando o cliente estiver conectado a essa rede. Os endereços salvos pelo usuário são automaticamente limpos quando o cliente do Teams é desmarcado.


## <a name="location-precedence"></a>Precedência de local

Os endereços de emergência para o Teams podem ser categorizados por tipos diferentes. A lista a seguir mostra a precedência de local usada quando um número de emergência é discado:

1. Um endereço adquirido dinamicamente definido pelo administrador do locatário no Serviço de Informações de Localização.

2. Um endereço que o usuário final confirmou, editou ou inseriu manualmente, que está associado à rede local à qual o cliente do Teams está conectado.

3. Um endereço sugerido automaticamente pelo sistema operacional.

4. Um endereço que o administrador atribui estaticamente ao usuário.


## <a name="emergency-address-classification-and-routing"></a>Classificação e roteamento de endereços de emergência

A tabela a seguir mostra os tipos de endereços de emergência e os métodos de roteamento associados para cada tipo: se a chamada é roteada automaticamente para o PSAP de serviço ou é filtrada para obter precisão antes de transferir para o PSAP de serviço. Esse comportamento de roteamento tem suporte no Estados Unidos para todos os usuários do Plano de Chamada, parceiros do Operator Connect e provedores de serviços de chamada de emergência certificados pelo Roteamento Direto.


| Tipo de endereço de emergência | Método de roteamento de emergência |
| :------------| :-------|
| Endereço de emergência adquirido dinamicamente definido pelo administrador. | Direto para PSAP. |
| Endereço de emergência obtido do sistema operacional sem **confirmação de precisão** pelo usuário. | Telado e transferido para PSAP. |
| Endereço de emergência obtido do sistema operacional **com confirmação de precisão** pelo usuário.| Direto para PSAP. |
| Endereço de emergência obtido do sistema operacional e editado e confirmado pelo usuário. | Telado e transferido para PSAP. |
| Endereço de emergência inserido e confirmado pelo usuário. | Telado e transferido para PSAP. |
| Endereço de emergência atribuído estaticamente ao usuário/número. | Telado e transferido para PSAP. |
| Null | Telado e transferido para PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permitir que os usuários finais configurem seu endereço de emergência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para políticas **de Emergência** > **de Voz**.
2. Selecione **Adicionar**.
3. Insira um nome para a política de chamada de emergência, por exemplo, "E911WFH".
4. Ative **o modo de pesquisa de localização externa**.
5. Selecione **Aplicar**.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Atribuir uma política de chamada de emergência personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>Usando o Windows PowerShell

Para habilitar esse recurso para os usuários finais, use o cmdlet New-CsTeamsEmergencyCallingPolicy PowerShell e defina o parâmetro ExternalLocationLookupMode como Habilitado. Veja o exemplo a seguir: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Depois de habilitar esse recurso para os usuários finais, na guia Chamadas, o usuário pode adicionar, editar ou confirmar um endereço de emergência e exibir o endereço depois de definido. Para obter mais informações sobre como os usuários finais podem definir serviços de localização, consulte [Work from Home Emergency 911: habilitar serviços de localização](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

No Windows, você pode gerenciar o serviço de localização do Windows e se os aplicativos têm acesso ao local, usando a política de grupo ou usando o [MDM (gerenciamento de dispositivo móvel).](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Para obter mais informações sobre o serviço de localização do Windows, consulte [o serviço de localização e a privacidade do Windows](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Observações e restrições

Considere o seguinte:

- A experiência de trabalho de casa descrita é para a área de trabalho do Teams no Windows e no Mac.

- Os telefones do Teams não dão suporte à experiência de trabalho em casa.

- O Teams Mobile dá suporte à detecção automática de localização, mas não à experiência inserida pelo usuário descrita.

- As configurações de privacidade podem entrar em conflito com a detecção automática de localização – Gerenciamento de Dispositivos dispositivos móveis podem ser usados.


## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)

- [Work from Home Emergency 911: habilitar serviços de localização](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

