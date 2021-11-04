---
title: 'Gerenciar números de acesso de conferência discagem em Skype for Business Server '
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumo: saiba como gerenciar números de acesso de conferência discagem em Skype for Business Server.'
ms.openlocfilehash: bb7a6d51d953519f7ccef274c9aff106c78f278d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746017"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gerenciar números de acesso de conferência discagem em Skype for Business Server
 
**Resumo:** Saiba como gerenciar números de acesso de conferência discado Skype for Business Server.
  
Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada. 
  
Este tópico descreve como exibir, modificar ou excluir números de acesso de conferência discado existentes. Para obter mais informações sobre como criar números de acesso de discagem iniciais, consulte [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Exibir números de acesso de conferência discado

Você pode exibir números de acesso à conferência discada usando o Painel de Controle Skype for Business Server ou usando o Shell de Gerenciamento Skype for Business Server.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Exibir números de acesso discado usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação à esquerda, clique em **Conferências**, e então em **Número de acesso discado**.
    
4. Na página **Número de acesso de discagem**, clique no número de acesso que gostaria de visualizar.
    
5. Em **Editar**, marque a caixa **de seleção Mostrar Detalhes.**
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Exibir números de acesso discado usando Skype for Business Server Shell de Gerenciamento

Para exibir informações sobre números de acesso discado, use o cmdlet **Get-CsDialInConferencingAccessNumber.**
  
O comando a seguir retorna uma coleção de todos os números de acesso de conferência discada configurados para uso na organização: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Veja a seguir um exemplo do tipo de informação retornada:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Para obter mais informações, [consulte Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificar números de acesso de conferência discado

Você pode modificar números de acesso discado usando Skype for Business Server Painel de Controle ou usando o Shell de Gerenciamento Skype for Business Server.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificar números de acesso discado usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação à esquerda, clique em **Conferências**, e então em **Número de acesso discado**.
    
4. Na página **Número de Acesso** discado, clique em um dos números de acesso discado na lista, clique em **Editar** e em **Mostrar detalhes.**
    
    > [!NOTE]
    > Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado. 
  
5. Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência. 
    
    Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.
    
6. Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem. Esse é o nome associado ao número de acesso discado nos Skype for Business de pesquisa.
    
    Esse nome é exibido no cliente quando um usuário disca o número de acesso. 
    
7. Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, `tel:+14255550200`.
    
    > [!NOTE]
    > O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada. 
  
8. Em **URI do SIP**, faça o seguinte:
    
   Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada. Esse URI SIP é exibido em vários locais, incluindo, mas não se limitando a mensagens de notificação de chamada e versões anteriores de clientes do Lync.
    
    > [!NOTE]
    > O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso. 
  
   Na caixa lista listada, clique no domínio do aplicativo Atendedor de Conferência que dá suporte a esse número de acesso discado.
    
9. Em **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.
    
    > [!NOTE]
    > Se foi preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do **Move-CsApplicationEndpoint** cmdlet ou excluir e recriar o número de acesso.
  
10. Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas nesse número de acesso. 
    
    O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.
    
11. (Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**. 
    
    É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.
    
12. Para adicionar uma região para o número de acesso de discagem, em Regiões Associadas, clique em Adicionar **,** clique em uma ou mais regiões associadas aos planos de discagem para esse número de acesso de discagem e clique em **OK**.
    
13. Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.
    
14. Clique em **Confirmar**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificar números de acesso discado usando Skype for Business Server Shell de Gerenciamento

Para modificar números de acesso discado, use o cmdlet **Set-CsDialInConferencingAccessNumber.**
  
O comando a seguir modifica a propriedade DisplayName para o número de acesso de conferência discado com a identidade sip:RedmondDialIn@litwareinc.com. Neste exemplo, o nome de exibição é definido como "Redmond Dial-In Access Number":
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

No próximo exemplo, o número de acesso à conferência discada com a identidade sip:RedmondDialIn@litwareinc.com é modificado para incluir duas regiões: Redmond e Seattle. Para isso, o parâmetro Regions é chamado, seguido das duas regiões (dois valores da cadeia de caracteres separados por vírgulas). Observe que haverá falha nesse comando, a menos que as regiões Redmond e Seattle já tenham sido definidas em planos de discagem.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Para obter mais informações, [consulte Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Excluir um número de acesso de conferência discado

Você pode excluir um número de acesso de conferência discada usando o Painel de Controle Skype for Business Server ou usando o Shell de Gerenciamento Skype for Business Server.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Excluir um número de acesso de conferência discada usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação à esquerda, clique em **Conferências**, e então em **Número de acesso discado**.
    
4. Na página, clique no número de discagem que deseja excluir da lista, clique em **Editar** e clique em **Excluir**.
    
5. Clique em **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Excluir um número de acesso de conferência discada usando Skype for Business Server Shell de Gerenciamento

Para excluir um número de acesso de conferência discada, use **Remove-CsDialInConferencingAccessNumber**.
  
O comando a seguir exclui o número de acesso de conferência discado com Identity sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

O próximo comando exclui todos os números de acesso de conferência discada associados à região Noroeste:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

O próximo comando exclui todos os números de acesso de conferência discagem em que o italiano é o idioma principal:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Para obter mais informações, [consulte Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
