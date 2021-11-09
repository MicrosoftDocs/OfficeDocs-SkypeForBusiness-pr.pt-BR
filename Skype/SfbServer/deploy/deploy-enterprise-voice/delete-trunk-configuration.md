---
title: 'Skype for Business Server: excluir uma coleção existente de configurações de tronco SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: saiba como excluir uma coleção de configurações de tronco usando o painel Skype for Business Server Controle.'
ms.openlocfilehash: d438db687c8af918a1ac0da67542048ac2fa0bae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860878"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server: excluir uma coleção existente de configurações de tronco SIP 
 
**Resumo:** Saiba como excluir uma coleção de definições de configuração de tronco usando o painel Skype for Business Server Controle.
  
As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) do IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos
    
- As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados
    
- Se a criptografia SRTP (Protocolo de Transporte em Tempo Real Seguro) é necessária ou não em cada tronco
    
Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Essa coleção global de configurações não pode ser excluída. No entanto, você pode usar o painel de controle Skype for Business Server ou o cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) para "redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se você definiu a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.
  
Os administradores também podem criar configurações personalizadas de tronco no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas. Ao remover essas configurações personalizadas, lembre-se das seguintes coisas:
  
- Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, se elas existirem. Se as configurações do site não existirem, esses troncos serão gerenciados pela coleção global de configurações de tronco.
    
- Se você remover as configurações com escopo de site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pela coleção global de configurações de tronco.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para remover as configurações de tronco com Skype for Business Server Painel de Controle

1. Em Skype for Business Server Painel de Controle, clique em **Roteamento** de Voz e clique em **Configuração de Tronco.**
    
2. Na guia **Configuração do** Tronco, selecione a coleção de configurações de tronco SIP a serem excluídas, clique em **Editar** e clique em **Excluir**. Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, segure a tecla Ctrl e clique em quaisquer outras coleções que você deseja remover.
    
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
    
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
    
5. Na caixa **Skype for Business Server Painel de Controle,** clique em **OK**.
    
6. Se você mudar de ideia e decidir não excluir a coleção, clique em **Confirmação** e, em seguida, clique em Cancelar Todas as Alterações **Não Confirmados**. Quando a **caixa Skype for Business Server painel de controle** for exibida, clique em **OK**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Removendo a configuração de tronco Configurações usando cmdlets Skype for Business Server Shell de Gerenciamento

Você pode excluir as configurações de tronco usando o Shell de Gerenciamento Skype for Business Server e o cmdlet **Remove-CsTrunkConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota do Shell de Gerenciamento Skype for Business Server Gerenciamento.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Para remover uma coleção especificada de configurações

- O comando a seguir remove as configurações de tronco aplicadas ao site redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para remover todas as coleções aplicadas ao escopo do site

- Este comando remove todas as configurações de tronco aplicadas ao escopo de serviço:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para remover todas as coleções em que o bypass de mídia está habilitado

- O comando a seguir remove todas as configurações de tronco onde o bypass de mídia foi habilitado:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/remove-cstrunkconfiguration)
