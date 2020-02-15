---
title: Excluir um conjunto existente de definições de configuração do tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045053"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Excluir um conjunto existente de definições de configuração do tronco SIP no Skype for Business Server

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Skype for Business Server, uma coleção global de definições de configuração do tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o painel ServerControl do Skype for Business ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se você tiver definido a propriedade Enable3pccRefer como true, ao redefinir a coleção global, a propriedade Enable3pccRefer será revertida para o valor padrão false.

Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas. Ao remover essas configurações personalizadas, lembre-se do seguinte:

- Se você remover as configurações de escopo de serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao seu site, caso existam. Se as configurações do site não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.
- Se você remover as configurações no escopo do site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pelo conjunto global de definições de configuração de tronco.

**Para remover as definições de configuração de tronco com o painel de controle do Skype for Business Server** 

1. No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e em **configuração de tronco**.
2. Na guia **configuração de tronco** , selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar**e em **excluir**. Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída e, em seguida, pressione a tecla CTRL e clique em qualquer coleção adicional que você deseja remover.
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
5. Na caixa de diálogo **painel de controle do Skype for Business Server** , clique em **OK**.
6. Se você mudar de ideia e optar por não excluir a coleção, clique em **confirmar**e em **cancelar todas as alterações não confirmadas**. Quando a caixa de diálogo **painel de controle do Skype for Business Server** for exibida, clique em **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de tronco usando cmdlets do Windows PowerShell


Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

**Para remover uma coleção especificada de configurações**

O comando a seguir remove as definições de configuração do tronco aplicadas ao site Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para remover todas as coleções aplicadas ao escopo do site**

Este comando Remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para remover todas as coleções nas quais o bypass de mídia está habilitado**

O comando a seguir remove todas as definições de configuração de tronco em que o bypass de mídia foi habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .
