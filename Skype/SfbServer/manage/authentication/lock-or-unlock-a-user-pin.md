---
title: Bloquear ou desbloquear um PIN de usuário no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumo: Bloqueie ou desbloqueie o PIN de conferência discada de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828361"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloquear ou desbloquear um PIN de usuário no Skype for Business Server
 
**Resumo:** Bloquear ou desbloquear o PIN de conferência discada de um usuário para o Skype for Business Server.
  
Você pode bloquear ou desbloquear o PIN de um usuário na seção **Usuários** do Painel de Controle do Skype for Business Server.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para bloquear o PIN de um usuário no Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Utilize um dos métodos a seguir para localizar um usuário:
    
    - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
    - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.
    
5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**. 
  
   e. Clique em **Localizar**.
    
   f. Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para desbloquear o PIN de um usuário no Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Utilize um dos métodos a seguir para localizar um usuário:
    
   - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
   - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.
    
5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**. 
  
   e. Clique em **Localizar**.
    
   f. Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloquear e desbloquear PINs de usuário usando cmdlets do Windows PowerShell

Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin usuário. Você pode executar esses cmdlets no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-lock-a-user-pin"></a>Para bloquear um PIN de usuário

- Para bloquear o PIN de um usuário, use o Lock-CsClientPin cmdlet. Por exemplo:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Para desbloquear um PIN de usuário

- Para desbloquear o PIN de um usuário, use o Unlock-CsClientPin cmdlet. Por exemplo:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin.](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)
