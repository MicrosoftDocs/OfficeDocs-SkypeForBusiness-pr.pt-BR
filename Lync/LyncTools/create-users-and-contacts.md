---
title: Criar usuários e contatos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="c0302-102">Criar usuários e contatos</span><span class="sxs-lookup"><span data-stu-id="c0302-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0302-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c0302-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c0302-104">Você deve usar a ferramenta de provisionamento de usuário (UserProvisioningTool.exe) do Lync Server 2013 para criar usuários e contatos em preparação para testes de carga de estresse e desempenho.</span><span class="sxs-lookup"><span data-stu-id="c0302-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="c0302-105">Veja a seguir uma lista de termos e definições que podem ser úteis ao ler este tópico.</span><span class="sxs-lookup"><span data-stu-id="c0302-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="c0302-106">Unidade organizacional – a unidade organizacional (OU) do Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="c0302-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="c0302-107">Federado/Cross pool – usuários que serão habilitados para se comunicar com os usuários de outros serviços de mensagens instantâneas (IM), como a rede do MSN de serviços de Internet, AOL® e Yahoo \! ®.</span><span class="sxs-lookup"><span data-stu-id="c0302-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="c0302-108">Listas de distribuição – os objetos nos serviços de domínio do Active Directory que contêm uma lista de usuários dos serviços de domínio Active Directory, usados para iniciar comunicações com grupos de pessoas.</span><span class="sxs-lookup"><span data-stu-id="c0302-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="c0302-109">Serviço de informações de local – o serviço do Lync Server 2013 que, quando habilitado e configurado por telefone, permite a recuperação do local físico para os serviços avançados de 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="c0302-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="c0302-110">Números de telefone dos EUA – os números de telefone atribuídos aos usuários, além do URI SIP usado para rotear chamadas de entrada e de saída e pesquisa de número reverso (RNL).</span><span class="sxs-lookup"><span data-stu-id="c0302-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="c0302-111">Criar usuários e contatos usando o UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="c0302-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="c0302-112">Você deve usar a ferramenta de provisionamento de usuário do Lync Server para criar usuários e contatos para simulação de carga.</span><span class="sxs-lookup"><span data-stu-id="c0302-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="c0302-113">A ferramenta de provisionamento de usuário do Lync Server é instalada com o pacote de ferramentas de desempenho e stress do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c0302-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="c0302-114">Certifique-se de que o instalador de pacotes (CapacityPlanningTool.msi) tenha sido executado no servidor front-end ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0302-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="c0302-115">Inicie a ferramenta de provisionamento de usuário do Lync Server executando o arquivo UserProvisioningTool.exe (localizado em% InstalledDirectory% LyncStressAndPerfTool \\ LyncStress) no servidor front-end ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c0302-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c0302-116">Você deve estar conectado como um membro do grupo de segurança Administradores de domínio para poder executar UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="c0302-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="c0302-117">É necessário executar a partir desse contexto porque UserProvisioningTool.exe será criar e configurar novos usuários dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0302-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c0302-118">Quando você cria um número significativo de usuários (10.000 ou mais), execute UserProvisioningTool.exe de um computador high-end.</span><span class="sxs-lookup"><span data-stu-id="c0302-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="c0302-119">Observe que o controlador de domínio também terá alta carga enquanto os usuários estão sendo criados.</span><span class="sxs-lookup"><span data-stu-id="c0302-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="c0302-120">Quando a ferramenta de provisionamento de usuário do Lync Server abrir, clique em **configuração** e selecione **carregar configuração**.</span><span class="sxs-lookup"><span data-stu-id="c0302-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="c0302-121">Para começar a configurar usuários e contatos, carregue o arquivo padrão incluído no pacote SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="c0302-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="c0302-122">Isso preencherá os campos com dados de exemplo que você precisará revisar para o seu sistema.</span><span class="sxs-lookup"><span data-stu-id="c0302-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="c0302-123">Se você tiver um arquivo XML pré-configurado que já contém as configurações personalizadas, carregue esse arquivo em vez disso.</span><span class="sxs-lookup"><span data-stu-id="c0302-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="c0302-124">Preencha os campos da ferramenta de provisionamento de usuário do Lync Server, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0302-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="c0302-125">![Guia criação de usuário.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Guia criação de usuário.")</span><span class="sxs-lookup"><span data-stu-id="c0302-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="c0302-126">Para configurar as opções de servidor, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c0302-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="c0302-127">Em **FQDN do pool de front-ends**, digite o FQDN (nome de domínio totalmente qualificado) do servidor Standard Edition ou pool de front-ends onde você deseja hospedar os usuários.</span><span class="sxs-lookup"><span data-stu-id="c0302-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="c0302-128">Em **prefixo de nome de usuário**, digite um prefixo que você deseja usar para criar nomes de usuário para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="c0302-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="c0302-129">Em **senha**, especifique uma senha que será aplicada a todas as contas de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="c0302-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="c0302-130">Em **domínio SIP**, digite o nome de domínio a ser usado para testar os URIs SIP dos usuários (identificadores de recursos uniformes).</span><span class="sxs-lookup"><span data-stu-id="c0302-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="c0302-131">Em **domínio da conta**, digite o nome de domínio do domínio atual dos serviços de domínio do Active Directory, no qual você deseja criar os usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="c0302-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="c0302-132">Em **unidade organizacional**, digite o nome da UO dos serviços de domínio do Active Directory em que você deseja criar os objetos de usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="c0302-133">Se a OU não existir, ela será criada.</span><span class="sxs-lookup"><span data-stu-id="c0302-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="c0302-134">Em **código de área de telefone**, digite o código de área de três dígitos que será usado para testar contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="c0302-135">Certifique-se de que o código de área do telefone não entra em conflito com os códigos de área dos outros usuários nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0302-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="c0302-136">Marque a caixa de seleção **habilitado para voz** se quiser habilitar os usuários de teste para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c0302-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="c0302-137">Em **número de usuários**, especifique o número total de usuários de teste que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="c0302-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="c0302-138">Em **Iniciar índice**, especifique o número inicial que será usado como sufixo para o prefixo de nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="c0302-139">Botão criar usuários</span><span class="sxs-lookup"><span data-stu-id="c0302-139">Create Users Button</span></span>

<span data-ttu-id="c0302-140">Quando você clicar no botão criar usuários, ele validará todos os parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0302-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="c0302-141">Se houver algum erro de validação, ele solicitará que você corrija os valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0302-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="c0302-142">Se todos os valores de entrada estiverem corretos, ele começará a criar usuários nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0302-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="c0302-143">Uma barra de progresso será exibida na parte inferior deste formulário.</span><span class="sxs-lookup"><span data-stu-id="c0302-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="c0302-144">Recomendamos que você não feche o aplicativo enquanto a barra de progresso estiver ativa.</span><span class="sxs-lookup"><span data-stu-id="c0302-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="c0302-145">A criação do usuário é um processo lento.</span><span class="sxs-lookup"><span data-stu-id="c0302-145">User Creation is a slow process.</span></span> <span data-ttu-id="c0302-146">Pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c0302-146">It can take several minutes.</span></span> <span data-ttu-id="c0302-147">Se o número de usuários for muito grande, o processo pode até levar algumas horas.</span><span class="sxs-lookup"><span data-stu-id="c0302-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="c0302-148">Se os usuários já existirem, eles serão atualizados com qualquer alteração.</span><span class="sxs-lookup"><span data-stu-id="c0302-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="c0302-149">Você pode validar que os usuários foram criados fazendo logon como um dos usuários no intervalo.</span><span class="sxs-lookup"><span data-stu-id="c0302-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="c0302-150">Use o prefixo de usuário, número de usuário e @sipDomain como o nome de usuário (por exemplo, LyncUser10@contoso.net), junto com a senha especificada.</span><span class="sxs-lookup"><span data-stu-id="c0302-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="c0302-151">Botão excluir usuários</span><span class="sxs-lookup"><span data-stu-id="c0302-151">Delete Users Button</span></span>

<span data-ttu-id="c0302-152">Quando você clicar no botão excluir usuários, ele validará todos os parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0302-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="c0302-153">Se houver algum erro de validação, ele solicitará que você corrija os valores de entrada.</span><span class="sxs-lookup"><span data-stu-id="c0302-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="c0302-154">Se todos os valores de entrada estiverem corretos, ele começará a desabilitar e excluir usuários nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0302-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="c0302-155">Uma barra de progresso será exibida na parte inferior deste formulário.</span><span class="sxs-lookup"><span data-stu-id="c0302-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="c0302-156">Recomendamos que você não feche o aplicativo enquanto a barra de progresso estiver ativa.</span><span class="sxs-lookup"><span data-stu-id="c0302-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="c0302-157">Há suporte apenas para números de telefone formatados para os EUA.</span><span class="sxs-lookup"><span data-stu-id="c0302-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="c0302-158">Os números de telefone sempre são atribuídos aos usuários, e todos os usuários criados por UserProvisioningTool.exe estão habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c0302-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="c0302-159">Todos os cenários que usam o número de telefone, como atendedor automático de conferência ou chamadas UC-PSTN, use este número de telefone para rotear chamadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="c0302-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="c0302-160">Por esse motivo, cada usuário deve ter um número de telefone exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c0302-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="c0302-161">Se você precisar criar usuários duas vezes, o comando falhará, a menos que você use um código de área diferente, ou se os usuários anteriores foram desabilitados usando o cmdlet <STRONG>Disable-CsUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c0302-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="c0302-162">Antes de criar contatos, você deve primeiro concluir a replicação do usuário, executado na guia usuários. Se você acabou de criar seus usuários, deverá aguardar até que a replicação do Lync Server seja concluída e preencha as contas de usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c0302-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="c0302-163">Se os usuários não tiverem concluído a replicação, você verá um erro.</span><span class="sxs-lookup"><span data-stu-id="c0302-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="c0302-164">Você saberá quando os usuários terminaram de replicar se o serviço front-end do Lync Server 2013 foi iniciado ou executando com êxito o cmdlet <STRONG>Get-CsUser</STRONG> no último usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="c0302-165">Guia de criação de contatos</span><span class="sxs-lookup"><span data-stu-id="c0302-165">Contacts Creation Tab</span></span>

<span data-ttu-id="c0302-166">A guia criação de contatos permite que você especifique detalhes dos contatos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c0302-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="c0302-167">![Guia criação de contatos.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Guia criação de contatos.")</span><span class="sxs-lookup"><span data-stu-id="c0302-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="c0302-168">Para configurar os contatos dos usuários, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c0302-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="c0302-169">Em média de contatos por usuário, especifique o número médio de contatos que serão preenchidos em listas de contatos para cada um dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c0302-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="c0302-170">Marque a caixa de seleção fixa se quiser criar um número igual de contatos para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="c0302-171">Se você quiser variar o número de contatos criados para usuários, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="c0302-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="c0302-172">Em média de grupos de contatos por usuário, especifique o número de grupos de contato por usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="c0302-173">Esse número deve ser menor do que a média de contatos por usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="c0302-174">Em porcentagem de contatos federados/entre pools, especifique um número entre 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="c0302-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="c0302-175">Essa porcentagem de contatos será criada com os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="c0302-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="c0302-176">Em prefixo de usuário federado/Cross pool, especifique o nome de usuário para usuários federados que serão adicionados às listas de contatos de usuários locais.</span><span class="sxs-lookup"><span data-stu-id="c0302-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="c0302-177">No domínio SIP/usuário de pool cruzado, especifique o nome de domínio SIP dos usuários federados.</span><span class="sxs-lookup"><span data-stu-id="c0302-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0302-178">Nenhum dos usuários deve estar conectado durante a criação de contatos.</span><span class="sxs-lookup"><span data-stu-id="c0302-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="c0302-179">Na guia criação de usuário, verifique se os parâmetros estão corretos.</span><span class="sxs-lookup"><span data-stu-id="c0302-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="c0302-180">O intervalo de usuários para o qual os contatos serão criados será obtido na guia criação de usuário.</span><span class="sxs-lookup"><span data-stu-id="c0302-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="c0302-181">Clique em criar contatos para começar a criação do contato.</span><span class="sxs-lookup"><span data-stu-id="c0302-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="c0302-182">Esse processo pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c0302-182">This process can take several minutes.</span></span> <span data-ttu-id="c0302-183">Após a conclusão, será exibida uma caixa de diálogo com a mensagem "operação concluída com êxito".</span><span class="sxs-lookup"><span data-stu-id="c0302-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="c0302-184">Você pode validar os contatos que foram criados fazendo logon como um usuário que foi criado na guia criação de usuários.</span><span class="sxs-lookup"><span data-stu-id="c0302-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0302-185">Após a criação dos contatos, essa ferramenta reiniciará todos os servidores front-end no pool de destino.</span><span class="sxs-lookup"><span data-stu-id="c0302-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="c0302-186">Pode levar mais tempo (até 2 horas) para que os servidores front-end sejam iniciados, dependendo de quantos contatos foram criados por essa operação.</span><span class="sxs-lookup"><span data-stu-id="c0302-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="c0302-187">Lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="c0302-187">Distribution List</span></span>

<span data-ttu-id="c0302-188">Um dos recursos da ferramenta de estresse e desempenho do Lync Server 2013 é simular o recurso de expansão da lista de distribuição (DL) no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c0302-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="c0302-189">Se não for habilitar a expansão de DL no UserProvisioningTool, você poderá pular esta etapa.</span><span class="sxs-lookup"><span data-stu-id="c0302-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="c0302-190">![Guia criação da lista de distribuição.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Guia criação da lista de distribuição.")</span><span class="sxs-lookup"><span data-stu-id="c0302-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="c0302-191">A guia lista de distribuição permite que você crie DLs que a ferramenta de estresse e desempenho usará para o recurso de expansão de lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="c0302-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="c0302-192">Antes de criar DLs, o Lync Server 2013 já deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="c0302-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="c0302-193">Você deve ter executado o Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="c0302-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="c0302-194">Caso contrário, os atributos DL não existirão no esquema dos serviços de domínio Active Directory e a ferramenta não poderá criar DLs.</span><span class="sxs-lookup"><span data-stu-id="c0302-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="c0302-195">Para configurar as listas de distribuição, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c0302-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="c0302-196">Em número de listas de distribuição, especifique o número total de DLs que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="c0302-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="c0302-197">(Recomendamos que você comece com o dobro do número de usuários).</span><span class="sxs-lookup"><span data-stu-id="c0302-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="c0302-198">Eles são numerados de 0 a n-1.</span><span class="sxs-lookup"><span data-stu-id="c0302-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="c0302-199">Em prefixo da lista de distribuição, especifique o prefixo que a DLs terá.</span><span class="sxs-lookup"><span data-stu-id="c0302-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="c0302-200">Por exemplo, se você especificar 100 DLs e um prefixo de testDL, as DLs serão nomeadas como testDL0, testDL1 e assim por diante, por meio de testDL99.</span><span class="sxs-lookup"><span data-stu-id="c0302-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="c0302-201">Em Membros mínimos em um dist. List, especifique o número mínimo de usuários a adicionar em cada lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="c0302-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="c0302-202">No máximo de membros em um dist. List, especifique o número máximo de usuários a adicionar em cada lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="c0302-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="c0302-203">Botão criar listas de distribuição</span><span class="sxs-lookup"><span data-stu-id="c0302-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="c0302-204">Quando você clica no botão criar listas de distribuição, a ferramenta consulta os serviços de domínio do Active Directory para ver se as listas de distribuição que correspondem ao prefixo e aos números já existem.</span><span class="sxs-lookup"><span data-stu-id="c0302-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="c0302-205">A ferramenta criará apenas aqueles que ainda não existem.</span><span class="sxs-lookup"><span data-stu-id="c0302-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="c0302-206">Ao adicionar membros a essas listas de distribuição recém-criadas, ele selecionará os usuários do intervalo especificado na guia criação de usuários.</span><span class="sxs-lookup"><span data-stu-id="c0302-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="c0302-207">Guia config do serviço de informações de local</span><span class="sxs-lookup"><span data-stu-id="c0302-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="c0302-208">Um dos recursos da ferramenta de estresse e desempenho do Lync Server 2013 é para gerar arquivos de configuração fictícios para o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="c0302-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="c0302-209">O serviço de informações de local normalmente não tem impacto significativo no desempenho dos servidores.</span><span class="sxs-lookup"><span data-stu-id="c0302-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="c0302-210">![Guia config do serviço de informações de local.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Guia config do serviço de informações de local.")</span><span class="sxs-lookup"><span data-stu-id="c0302-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="c0302-211">Se você optar por testar esse recurso, preencha os valores mencionados no formulário e, em seguida, clique no botão gerar arquivos de configuração de LIS.</span><span class="sxs-lookup"><span data-stu-id="c0302-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="c0302-212">Ele irá gerar arquivos CSV chamados LIS \_Subnet.csv, lis \_Switches.csv, Lis \_Ports.csv e Lis \_WAP.csv.</span><span class="sxs-lookup"><span data-stu-id="c0302-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="c0302-213">Você pode então importar esses arquivos CSV para o banco de dados LIS usando o cmdlet **set-CsLisSubnet** , o cmdlet **set-CsLisSwitch** , o cmdlet **set-CsLisPort** e o cmdlet **set-CsWirelessAccessPoint** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c0302-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

