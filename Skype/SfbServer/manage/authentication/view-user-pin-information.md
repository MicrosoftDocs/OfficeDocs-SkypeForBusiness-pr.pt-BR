---
title: Exibir informações de PIN do usuário no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumo: Exibir informações de PIN do usuário no Skype for Business Server.'
ms.openlocfilehash: a77dbc71a186ff20b0136b3391f5ce33dcda1134
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014185"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Exibir informações de PIN do usuário no Skype for Business Server
 
**Resumo:** Exibir informações de PIN do usuário Skype for Business Server.
  
Para ingressar em uma conferência discada como um usuário autenticado, um usuário Skype for Business Server com credenciais do Active Directory Domain Services (AD DS) requer um PIN (número de identificação pessoal). Você pode exibir as informações de PIN de um usuário Skype for Business Server Painel de Controle.
  
> [!NOTE]
> Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN. Se um usuário tiver perdido o PIN, você poderá [redefini-lo](set-a-user-s-dial-in-conferencing-pin.md) seguindo os procedimentos em Definir o PIN de conferência discada do usuário em Skype for Business Server
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para exibir o PIN de um usuário no painel Skype for Business Server Controle

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
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de PIN do usuário usando Windows PowerShell cmdlets

Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-user-pin-information"></a>Para exibir as informações de PIN do usuário

Para exibir informações de PIN para um usuário, digite um comando semelhante ao seguinte no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Isto retorna informações semelhantes à seguinte:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsConferenceDisclaimer.](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>Confira também

[Defina o PIN de conferência discado de um usuário em Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear ou desbloquear um PIN de usuário Skype for Business Server](lock-or-unlock-a-user-pin.md)