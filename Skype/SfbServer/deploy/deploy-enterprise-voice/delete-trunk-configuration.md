---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: Saiba como excluir um conjunto de definições de configuração de tronco usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836971"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
 
**Resumo:** Saiba como excluir um conjunto de definições de configuração de tronco usando o Painel de Controle do Skype for Business Server.
  
As definições de configuração do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) da IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos.
    
- As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.
    
- Se a criptografia SRTP (Secure Realtime Transport Protocol) é necessária ou não em cada tronco.
    
Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o Painel de Controle do Skype for Business Server ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) para "redefinir" as propriedades na coleção global com seus valores padrão. Por exemplo, se você tiver definido a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.
  
Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo de serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas. Ao remover essas configurações personalizadas, lembre-se do seguinte:
  
- Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações de site não existirem, esses troncos serão gerenciados pelo conjunto global de definições de configuração de tronco.
    
- Se você remover as definições de escopo do site, todos os troncos SIP gerenciados por essas definições agora serão gerenciados pelo conjunto global de definições de configuração do tronco.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para remover as definições de configuração de tronco com o Painel de Controle do Skype for Business Server

1. No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**
    
2. Na guia **Configuração do** Tronco, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e em **Excluir.** Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, mantenha a tecla Ctrl e clique nas coleções adicionais que deseja remover.
    
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
    
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
    
5. Na caixa **de diálogo Painel de Controle do Skype for Business Server,** clique em **OK.**
    
6. Se você mudar de ideia e decidir  não excluir a coleção, clique em Confirmação e em Cancelar Todas as Alterações **Não Confirmados.** Quando a caixa de diálogo Painel de Controle do **Skype for Business Server** for exibida, clique em **OK.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Removendo definições de configuração de tronco usando cmdlets do Shell de Gerenciamento do Skype for Business Server

Você pode excluir definições de configuração de tronco usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Remove-CsTrunkConfiguration.** Você pode executar esse cmdlet a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Shell de Gerenciamento do Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Para remover um conjunto especificado de configurações

- O comando a seguir remove as definições de configuração de tronco aplicadas ao site Redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para remover todos os coleções aplicados ao escopo do site

- Este comando remove todas as definições de configuração de tronco aplicadas ao escopo de serviço:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para remover todas as coleções onde o bypass de mídia está habilitado

- O comando a seguir remove todas as definições de configuração de tronco onde o bypass de mídia foi habilitado:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)
  

