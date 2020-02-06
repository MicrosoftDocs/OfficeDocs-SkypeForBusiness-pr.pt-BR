---
title: 'Gerenciar números de acesso à conferência discada no Skype for Business Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumo: saiba como gerenciar números de acesso de conferência discada no Skype for Business Server.'
ms.openlocfilehash: 48fae5535607c59931be1c7f5201c3c45a150417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818663"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gerenciar números de acesso à conferência discada no Skype for Business Server
 
**Resumo:** Saiba como gerenciar números de acesso de conferência discada no Skype for Business Server.
  
Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada. 
  
Este tópico descreve como exibir, modificar ou excluir números de acesso de conferência discada existentes. Para obter mais informações sobre como criar números de acesso de discagem iniciais, consulte [Configurar conferência discada no Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Visualizar números de acesso de conferência discada

Você pode exibir os números de acesso de conferência discada usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Exibir números de acesso de discagem usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página **Número de acesso de discagem**, clique no número de acesso que gostaria de visualizar.
    
5. Em **Editar**, selecione a caixa de verificação **Mostrar detalhes**.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Exibir números de acesso de discagem usando o Shell de gerenciamento do Skype for Business Server

Para exibir informações sobre números de acesso de discagem, use o cmdlet **Get-Cs DialInConferencingAccessNumber**.
  
O comando a seguir retorna uma coleção de todos os números de acesso à conferência discada configurados para uso na organização: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

A seguir temos um exemplo do tipo de informação retornado:
  
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

Para obter mais informações, consulte [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Modificar os números de acesso da conferência discada

Você pode modificar números de acesso de discagem usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificar números de acesso de discagem usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página **Número de Acesso de Discagem**, clique em um dos números de acesso de discagem na lista, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
    > [!NOTE]
    > Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado. 
  
5. Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência. 
    
    Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.
    
6. Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem. Este é o nome associado ao número de acesso de discagem nos resultados da pesquisa do Skype for Business.
    
    Esse nome é exibido no cliente quando um usuário disca o número de acesso. 
    
7. Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.
    
    > [!NOTE]
    > O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada. 
  
8. Em **URI do SIP**, faça o seguinte:
    
   Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada. Esse URI SIP é exibido em vários locais, incluindo, entre outros, mensagens de notificação de chamada e versões anteriores de clientes do Lync.
    
    > [!NOTE]
    > O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso. 
  
   Na caixa de listagem suspensa, clique no domínio do aplicativo de assistente de conferência que dá suporte a esse número de acesso à discagem.
    
9. Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.
    
    > [!NOTE]
    > Se for preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do **Move-CsApplicationEndpoint** ou excluir e recriar o número de acesso.
  
10. Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem. 
    
    O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.
    
11. (Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**. 
    
    É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.
    
12. Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em **Adicionar**, clique em uma ou mais regiões associadas aos planos de discagem para este número de acesso à discagem e, em seguida, clique em **OK**.
    
13. Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.
    
14. Clique em **Confirmar**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificar números de acesso de discagem usando o Shell de gerenciamento do Skype for Business Server

Para modificar os números de acesso de discagem, use o cmdlet **Set-Cs DialInConferencingAccessNumber**.
  
O comando a seguir modifica a propriedade DisplayName do número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com. Nesse exemplo, o nome para exibição é definido como "Redmond Dial-In Access Number".
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

No próximo exemplo, o número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com é modificado para incluir duas regiões: Redmond e Seattle. Para isso, o parâmetro Regions é chamado, seguido das duas regiões (dois valores da cadeia de caracteres separados por vírgulas). Observe que haverá falha nesse comando, a menos que as regiões Redmond e Seattle já tenham sido definidas em planos de discagem.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Para obter mais informações, consulte [set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Excluir um número de acesso de conferência discada

Você pode excluir um número de acesso à conferência discada usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Excluir um número de acesso à conferência discada usando o painel de controle do Skype for Business Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página, clique no número de discagem que deseja excluir da lista, clique em  **Editar**e, em seguida, clique em **Excluir**.
    
5. Clique em **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Excluir um número de acesso à conferência discada usando o Shell de gerenciamento do Skype for Business Server

Para excluir um número de acesso de conferência discada, use o **Remove-CsDialInConferencingAccessNumber**.
  
O comando a seguir exclui o número de acesso da conferência discada com Identity sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

O próximo comando exclui todos os números de acesso de conferência discada associados com a região Noroeste:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

O próximo comando exclui todos os números de acesso de conferência discada onde italiano é o idioma principal:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Para obter mais informações, consulte [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

