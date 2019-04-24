---
title: Bloquear ou desbloquear um PIN em Skype do usuário para o servidor de negócios
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumo: Bloquear ou desbloquear discada um usuário PIN para Skype para Business Server.'
ms.openlocfilehash: fb90cd54ac5f339050adc51378e42d2542e489fa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217905"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloquear ou desbloquear um PIN em Skype do usuário para o servidor de negócios
 
**Resumo:** Bloquear ou desbloquear discada um usuário PIN para Skype para Business Server.
  
Você pode bloquear ou desbloquear o PIN de um usuário da seção de **usuários** do Skype para painel de controle do servidor de negócios.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Bloquear o PIN de um usuário no Skype para painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Use um dos seguintes métodos para localizar um usuário:
    
    - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
    - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.
    
5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**. 
  
   f. Clique em **Localizar**.
    
   f. Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para desbloquear o PIN de um usuário no Skype para painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Use um dos seguintes métodos para localizar um usuário:
    
   - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
   - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.
    
5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**. 
  
   f. Clique em **Localizar**.
    
   f. Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloquear e desbloquear PINs de usuário usando Cmdlets do Windows PowerShell

Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin. Você pode executar esses cmdlets do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-lock-a-user-pin"></a>Para bloquear um PIN de usuário

- Para bloquear o PIN de um usuário, use o cmdlet Lock-CsClientPin. Por exemplo:
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Para desbloquear um PIN de usuário

- Para desbloquear o PIN de um usuário, use o cmdlet Unlock-CsClientPin. Por exemplo:
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .
