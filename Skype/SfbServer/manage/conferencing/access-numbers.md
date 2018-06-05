---
title: Gerenciar os números de acesso da conferência discada no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Resumo: Saiba como gerenciar os números de acesso de conferência discada em Skype para Business Server 2015.'
ms.openlocfilehash: 3bbde214863fa7d08214569e4d9aa2a767016eb4
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569432"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server-2015"></a><span data-ttu-id="c9f41-103">Gerenciar os números de acesso da conferência discada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c9f41-103">Manage dial-in conferencing access numbers in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c9f41-104">**Resumo:** Saiba como gerenciar os números de acesso de conferência discada em Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c9f41-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c9f41-105">Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências.</span><span class="sxs-lookup"><span data-stu-id="c9f41-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="c9f41-106">Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="c9f41-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="c9f41-107">Este tópico descreve como exibir, modificar ou excluir números de acesso de conferência discada existentes.</span><span class="sxs-lookup"><span data-stu-id="c9f41-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="c9f41-108">Para obter mais informações sobre como criar os números de acesso de discagem inicial, consulte [Configure a conferência discada no Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c9f41-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="c9f41-109">Visualizar números de acesso de conferência discada</span><span class="sxs-lookup"><span data-stu-id="c9f41-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="c9f41-110">Você pode exibir os números de acesso de conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c9f41-111">Exibir números de acesso discado usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c9f41-112">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c9f41-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c9f41-113">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c9f41-114">Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="c9f41-115">Na página **Número de acesso de discagem**, clique no número de acesso que gostaria de visualizar.</span><span class="sxs-lookup"><span data-stu-id="c9f41-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="c9f41-116">Em **Editar**, selecione a caixa de verificação **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c9f41-117">Exibir números de acesso discado usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c9f41-118">Para exibir informações sobre números de acesso de discagem, use o cmdlet **Get-Cs DialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="c9f41-119">O comando a seguir retorna uma coleção de todos os números de acesso de conferência discada configurados para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="c9f41-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="c9f41-120">A seguir temos um exemplo do tipo de informação retornado:</span><span class="sxs-lookup"><span data-stu-id="c9f41-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="c9f41-121">Para obter mais informações, consulte [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9f41-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="c9f41-122">Modificar os números de acesso da conferência discada</span><span class="sxs-lookup"><span data-stu-id="c9f41-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="c9f41-123">Você pode modificar os números de acesso discado usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c9f41-124">Modificar os números de acesso discado usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c9f41-125">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c9f41-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c9f41-126">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c9f41-127">Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="c9f41-128">Na página **Número de Acesso de Discagem**, clique em um dos números de acesso de discagem na lista, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9f41-p103">Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="c9f41-131">Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c9f41-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="c9f41-132">Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="c9f41-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="c9f41-133">Em **Nome de exibição**, digite uma descrição para o número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="c9f41-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="c9f41-134">Este é o nome que está associado ao número de acesso de discagem no Skype para resultados de pesquisa de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="c9f41-135">Este nome é exibido no cliente quando um usuário chama o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="c9f41-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="c9f41-p105">Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9f41-138">O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c9f41-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="c9f41-139">Em **URI do SIP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c9f41-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="c9f41-140">Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c9f41-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="c9f41-141">O URI do SIP é exibido em vários locais, incluindo, mas não limitado para chamar as mensagens de notificação e versões anteriores dos clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="c9f41-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9f41-p107">O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="c9f41-145">Na caixa de listagem suspensa, clique no domínio do aplicativo Atendedor de conferência que ofereça suporte a esse número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="c9f41-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="c9f41-146">Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="c9f41-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9f41-147">Se você precisar alterar o pool depois de criar o número de acesso, você deve usar o cmdlet **Move-CsApplicationEndpoint** ou excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="c9f41-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="c9f41-148">Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="c9f41-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="c9f41-p108">O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="c9f41-151">(Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="c9f41-p109">É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="c9f41-154">Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em * * Add * *, clique em uma ou mais regiões associadas com os planos de discagem para este número de acesso de discagem e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-154">To add a region for the dial-in access number, under **Associated regions**, click ** Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="c9f41-155">Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="c9f41-156">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c9f41-157">Modificar os números de acesso discado usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c9f41-158">Para modificar os números de acesso de discagem, use o cmdlet **Set-Cs DialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="c9f41-p110">O comando a seguir modifica a propriedade DisplayName do número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com. Nesse exemplo, o nome para exibição é definido como "Redmond Dial-In Access Number".</span><span class="sxs-lookup"><span data-stu-id="c9f41-p110">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="c9f41-p111">No próximo exemplo, o número de acesso da conferência discada com Identity sip:RedmondDialIn@litwareinc.com é modificado para incluir duas regiões: Redmond e Seattle. Para isso, o parâmetro Regions é chamado, seguido das duas regiões (dois valores da cadeia de caracteres separados por vírgulas). Observe que haverá falha nesse comando, a menos que as regiões Redmond e Seattle já tenham sido definidas em planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="c9f41-p111">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="c9f41-164">Para obter mais informações, consulte [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9f41-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="c9f41-165">Excluir um número de acesso de conferência discada</span><span class="sxs-lookup"><span data-stu-id="c9f41-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="c9f41-166">Você pode excluir um número de acesso de conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c9f41-167">Excluir um número de acesso de conferência discada usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c9f41-168">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c9f41-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2.  <span data-ttu-id="c9f41-169">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c9f41-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c9f41-170">Na barra de navegação à esquerda, clique em **Conferência**e, então, em  **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="c9f41-171">Na página, clique no número de discagem que deseja excluir da lista, clique em  **Editar**e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c9f41-172">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c9f41-173">Excluir um número de acesso de conferência discada usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c9f41-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c9f41-174">Para excluir um número de acesso de conferência discada, use o **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="c9f41-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="c9f41-175">O comando a seguir exclui o número de acesso da conferência discada com Identity sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="c9f41-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="c9f41-176">O próximo comando exclui todos os números de acesso de conferência discada associados com a região Noroeste:</span><span class="sxs-lookup"><span data-stu-id="c9f41-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="c9f41-177">O próximo comando exclui todos os números de acesso de conferência discada onde italiano é o idioma principal:</span><span class="sxs-lookup"><span data-stu-id="c9f41-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="c9f41-178">Para obter mais informações, consulte [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9f41-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

