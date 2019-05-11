---
title: Excluir um conjunto existente de definições de configuração de tronco SIP no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. '
ms.openlocfilehash: 144d40f45853b0d0e3031f9d491fa1a3b1491ba8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896313"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Excluir um conjunto existente de definições de configuração de tronco SIP no Skype para Business Server

Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. Essas configurações realizam atividades como especificar:

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.
- Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.

Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o Skype para negócios ServerControl painel ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) "Redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.

Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:

- Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.
- Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.

**Para remover as definições de configuração do tronco com o Skype para painel de controle do servidor de negócios** 

1. Na Skype para painel de controle do Business Server, clique em **Roteamento de voz**e clique em **Configuração de tronco**.
2. Na guia **Configuração do tronco** , selecione o conjunto de definições de configuração de tronco SIP a ser excluído, clique em **Editar**e, em seguida, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
5. Na caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.
6. Se você mudar de ideia e decide não exclua o conjunto, clique em **Confirmar**e clique em **Cancelar todas as alterações não confirmadas**. Quando for exibida a caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de tronco usando cmdlets do Windows PowerShell


Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

**Para remover uma coleção especificada das definições**

O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para remover todos os conjuntos aplicados ao escopo do site**

Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para remover todos os conjuntos em que o bypass de mídia está habilitado**

O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
