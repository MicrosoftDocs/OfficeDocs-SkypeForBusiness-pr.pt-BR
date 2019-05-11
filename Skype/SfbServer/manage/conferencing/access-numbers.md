---
title: 'Gerenciar os números de acesso de conferência discada em Skype para Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumo: Saiba como gerenciar os números de acesso de conferência discada em Skype para Business Server.'
ms.openlocfilehash: aa386b1c2dd868634539be32062ed7728e27c1e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919406"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Gerenciar os números de acesso de conferência discada em Skype para Business Server
 
**Resumo:** Saiba como gerenciar os números de acesso de conferência discada em Skype para Business Server.
  
Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada. 
  
Este tópico descreve como exibir, modificar ou excluir números de acesso de conferência discada existentes. Para obter mais informações sobre como criar os números de acesso de discagem inicial, consulte [Configure a conferência discada no Skype para Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Visualizar números de acesso de conferência discada

Você pode exibir os números de acesso de conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Exibir números de acesso discado usando Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página **Número de acesso de discagem**, clique no número de acesso que gostaria de visualizar.
    
5. Em **Editar**, selecione a caixa de verificação **Mostrar detalhes**.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Exibir números de acesso discado usando Skype do Shell de gerenciamento do servidor de negócios

Para exibir informações sobre números de acesso de discagem, use o cmdlet **Get-Cs DialInConferencingAccessNumber**.
  
O comando a seguir retorna uma coleção de todos os números de acesso de conferência discada configurados para uso na organização: 
  
```
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

Você pode modificar os números de acesso discado usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modificar os números de acesso discado usando Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página **Número de Acesso de Discagem**, clique em um dos números de acesso de discagem na lista, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
    > [!NOTE]
    > Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado. 
  
5. Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência. 
    
    Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.
    
6. Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem. Este é o nome que está associado ao número de acesso de discagem no Skype para resultados de pesquisa de negócios.
    
    Esse nome é exibido no cliente quando um usuário disca o número de acesso. 
    
7. Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.
    
    > [!NOTE]
    > O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada. 
  
8. Em **URI do SIP**, faça o seguinte:
    
   Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada. O URI do SIP é exibido em vários locais, incluindo, mas não limitado para chamar as mensagens de notificação e versões anteriores dos clientes do Lync.
    
    > [!NOTE]
    > O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso. 
  
   Na caixa de listagem suspensa, clique no domínio do aplicativo Atendedor de conferência que ofereça suporte a esse número de acesso de discagem.
    
9. Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.
    
    > [!NOTE]
    > Se for preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do **Move-CsApplicationEndpoint** ou excluir e recriar o número de acesso.
  
10. Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem. 
    
    O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.
    
11. (Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**. 
    
    É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.
    
12. Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em **Adicionar**, clique em uma ou mais regiões que estão associados com os planos de discagem para este número de acesso de discagem e clique em **Okey**.
    
13. Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.
    
14. Clique em **Confirmar**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modificar os números de acesso discado usando Skype do Shell de gerenciamento do servidor de negócios

Para modificar os números de acesso de discagem, use o cmdlet **Set-Cs DialInConferencingAccessNumber**.
  
O comando a seguir modifica a propriedade DisplayName do número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com. Nesse exemplo, o nome para exibição é definido como "Redmond Dial-In Access Number".
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

No próximo exemplo, o número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com é modificado para incluir duas regiões: Redmond e Seattle. Para isso, o parâmetro Regions é chamado, seguido das duas regiões (dois valores da cadeia de caracteres separados por vírgulas). Observe que haverá falha nesse comando, a menos que as regiões Redmond e Seattle já tenham sido definidas em planos de discagem.
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Para obter mais informações, consulte [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Excluir um número de acesso de conferência discada

Você pode excluir um número de acesso de conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Excluir um número de acesso de conferência discada usando o Skype para painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.
    
4. Na página, clique no número de discagem que deseja excluir da lista, clique em  **Editar**e, em seguida, clique em **Excluir**.
    
5. Clique em **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Excluir um número de acesso de conferência discada usando o Skype do Shell de gerenciamento do servidor de negócios

Para excluir um número de acesso de conferência discada, use o **Remove-CsDialInConferencingAccessNumber**.
  
O comando a seguir exclui o número de acesso da conferência discada com Identity sip:RedmondDialInAccess@litwareinc.com:
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

O próximo comando exclui todos os números de acesso de conferência discada associados com a região Noroeste:
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

O próximo comando exclui todos os números de acesso de conferência discada onde italiano é o idioma principal:
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Para obter mais informações, consulte [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

