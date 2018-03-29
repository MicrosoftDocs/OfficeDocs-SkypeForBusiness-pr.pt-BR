---
title: Exibir informações de PIN do usuário no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumo: Exibir as informações de PIN de usuário no Skype para Business Server 2015.'
ms.openlocfilehash: 2521c9edba0b16eda6ea799b6b968a8c57bba245
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="view-user-pin-information-in-skype-for-business-server-2015"></a>Exibir informações de PIN do usuário no Skype for Business Server 2015
 
**Resumo:** Usuário exibir informações de PIN no Skype para Business Server 2015.
  
Para ingressar na conferência discada como usuário autenticado, um Skype para usuário Business Server 2015 com credenciais do Active Directory Domain Services (AD DS) requer um número de identificação pessoal (PIN). Você pode exibir informações de PIN de um usuário do Skype de painel de controle do servidor de negócios.
  
> [!NOTE]
> Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN. Se um usuário tiver perdido seu PIN, você pode redefini-lo seguindo os procedimentos no [conjunto de discada um usuário PIN no Skype para Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para exibir o PIN de um usuário no Skype para painel de controle do servidor de negócios

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
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de PIN do usuário pelos cmdlets usando o Windows PowerShell

Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-view-user-pin-information"></a>Para exibir as informações de PIN do usuário

Para exibir informações de PIN de um usuário, digite um comando semelhante ao seguinte no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Isso retornará informações parecidas com:

  ```
  Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Consulte também

#### 

[Definir discada um usuário PIN no Skype para Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear ou desbloquear um PIN em Skype do usuário para Business Server 2015](lock-or-unlock-a-user-pin.md)

