---
title: Bloquear ou desbloquear um PIN de usuário Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumo: bloqueie ou desbloqueie o PIN de conferência discada de um usuário para Skype for Business Server.'
ms.openlocfilehash: 1ae1deea84b099852decd9acbc6315049484b0b3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848594"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloquear ou desbloquear um PIN de usuário Skype for Business Server
 
**Resumo:** Bloqueie ou desbloqueie o PIN de conferência discada de um usuário para Skype for Business Server.
  
Você pode bloquear ou desbloquear o PIN de um usuário na **seção Usuários** Skype for Business Server Painel de Controle.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para bloquear o PIN de um usuário Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
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
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para desbloquear o PIN de um usuário Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
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
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloqueio e desbloqueio de PINs do usuário usando Windows PowerShell cmdlets

Você pode bloquear e desbloquear PINs de usuário usando Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin de usuário. Você pode executar esses cmdlets no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-lock-a-user-pin"></a>Para bloquear um PIN de usuário

- Para bloquear o PIN de um usuário, use o cmdlet Lock-CsClientPin usuário. Por exemplo:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Para desbloquear um PIN de usuário

- Para desbloquear o PIN de um usuário, use o cmdlet Unlock-CsClientPin usuário. Por exemplo:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin.](/powershell/module/skype/unlock-csclientpin?view=skype-ps)