---
title: Skype for Business Server - Excluir uma coleção existente de configurações de tronco SIP
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway de rede telefônica pública comutado, uma troca de filial pública IP ou um Controlador de Borda de Sessão no provedor de serviços.
ms.openlocfilehash: 390e70040994dbd8474bda51b0d33bfc13c36697
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845414"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server - Excluir uma coleção existente de configurações de tronco SIP

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Essa coleção global de configurações não pode ser excluída. No entanto, você pode usar o painel Skype for Business ServerControl ou o cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se você definiu a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.

Os administradores também podem criar configurações personalizadas de tronco no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas. Ao remover essas configurações personalizadas, lembre-se do seguinte:

- Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, se elas existirem. Se as configurações do site não existirem, esses troncos serão gerenciados pela coleção global de configurações de tronco.
- Se você remover as configurações com escopo de site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pela coleção global de configurações de tronco.

**Para remover as configurações do tronco com o painel de Skype for Business Server De controle** 

1. No painel Skype for Business Server controle, clique em **Roteamento** de Voz e clique em **Configuração do Tronco.**
2. Na guia **Configuração do** Tronco, selecione a coleção de configurações de tronco SIP a serem excluídas, clique em **Editar** e clique em **Excluir**. Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, segure a tecla Ctrl e clique em quaisquer coleções adicionais que você deseja remover.
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
5. Na caixa **Skype for Business Server Painel de Controle,** clique em **OK**.
6. Se você mudar de ideia e decidir não excluir a coleção, clique em Confirmação **e,** em seguida, clique em Cancelar Todas as Alterações **Não Confirmados**. Quando a **caixa Skype for Business Server painel de controle** for exibida, clique em **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo configurações de tronco usando Windows PowerShell cmdlets


Você pode excluir as configurações de tronco usando Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

**Para remover uma coleção especificada de configurações**

O comando a seguir remove as configurações de tronco aplicadas ao site redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para remover todas as coleções aplicadas ao escopo do site**

Este comando remove todas as configurações de tronco aplicadas ao escopo de serviço:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para remover todas as coleções em que o bypass de mídia está habilitado**

O comando a seguir remove todas as configurações de tronco onde o bypass de mídia foi habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/Remove-CsTrunkConfiguration)
