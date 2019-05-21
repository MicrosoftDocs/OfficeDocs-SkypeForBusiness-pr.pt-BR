---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274930"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. Essas configurações realizam atividades como especificar:

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.
- Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o painel ServerControl do Skype for Business ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global para os valores padrão. Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.

Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:

- Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.
- Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.

**Para remover os parâmetros de configuração de tronco com o painel de controle do Skype for Business Server** 

1. No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.
2. Na guia **configuração de tronco** , selecione a coleção das configurações de tronco SIP a serem excluídas, clique em **Editar**e, em seguida, clique em **excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
5. Na caixa de diálogo **painel de controle do Skype for Business Server** , clique em **OK**.
6. Se você mudar de ideia e decidir não excluir a coleção, clique em **confirmar**e, em seguida, clique em **cancelar todas as alterações**não confirmadas. Quando a caixa de diálogo **painel de controle do Skype for Business Server** for exibida, clique em **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de tronco usando cmdlets do Windows PowerShell


Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

**Para remover uma coleção especificada das definições**

O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para remover todos os conjuntos aplicados ao escopo do site**

Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para remover todos os conjuntos em que o bypass de mídia está habilitado**

O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
