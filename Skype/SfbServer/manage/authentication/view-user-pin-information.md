---
title: Exibir informações de PIN do usuário no Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumo: exibir informações de PIN do usuário no Skype for Business Server.'
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818683"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Exibir informações de PIN do usuário no Skype for Business Server
 
**Resumo:** Exibir informações de PIN do usuário no Skype for Business Server.
  
Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Skype for Business Server com as credenciais dos serviços de domínio Active Directory (AD DS) requer um PIN (número de identificação pessoal). Você pode exibir as informações de PIN de um usuário no painel de controle do Skype for Business Server.
  
> [!NOTE]
> Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN. Se um usuário perde o PIN, você pode redefini-lo seguindo os procedimentos em [definir o PIN de conferência discada do usuário no Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para exibir o PIN de um usuário no painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
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
  
   vocálico. Clique em **Localizar**.
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de PIN do usuário usando cmdlets do Windows PowerShell

Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-user-pin-information"></a>Para exibir as informações de PIN do usuário

Para exibir as informações de PIN de um usuário, digite um comando semelhante ao seguinte no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Isso retornará informações parecidas com:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Confira também

[Definir o PIN de conferência discada de um usuário no Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear ou desbloquear um PIN de usuário no Skype for Business Server](lock-or-unlock-a-user-pin.md)
