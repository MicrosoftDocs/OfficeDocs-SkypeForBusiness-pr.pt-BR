---
title: 'Lync Server 2013: Configurando Estados de presença personalizados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="7b09e-102">Configuração de Estados de presença personalizada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b09e-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b09e-103">_**Tópico da última modificação:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="7b09e-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="7b09e-104">Para definir Estados de presença personalizada no Lync 2013, crie um arquivo de configuração de presença XML personalizada e especifique sua localização usando os cmdlets do Shell de gerenciamento do Lync Server **New-CSClientPolicy** ou **set-CSClientPolicy** com o parâmetro CustomStateURL.</span><span class="sxs-lookup"><span data-stu-id="7b09e-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="7b09e-105">Os arquivos de configuração têm as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="7b09e-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="7b09e-106">Estados de presença personalizada podem ser configurados com os indicadores de presença disponível, ocupado e não incomodar.</span><span class="sxs-lookup"><span data-stu-id="7b09e-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="7b09e-107">O atributo Availability determina qual indicador de presença está associado ao texto de status do estado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7b09e-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="7b09e-108">No exemplo mais adiante neste tópico, o texto de status que trabalha em casa é exibido à direita do indicador de presença verde (disponível).</span><span class="sxs-lookup"><span data-stu-id="7b09e-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="7b09e-109">O tamanho máximo do texto de status é de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7b09e-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="7b09e-110">No máximo quatro Estados de presença personalizados podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="7b09e-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="7b09e-111">O parâmetro CustomStateURL especifica o local do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7b09e-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="7b09e-112">No Lync 2013, o modo de alta segurança SIP é habilitado por padrão, portanto, você precisará armazenar o arquivo de configuração de presença personalizado em um servidor Web que tenha HTTPS habilitado.</span><span class="sxs-lookup"><span data-stu-id="7b09e-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="7b09e-113">Caso contrário, os clientes do Lync 2013 não poderão se conectar a ele.</span><span class="sxs-lookup"><span data-stu-id="7b09e-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="7b09e-114">Por exemplo, um endereço válido seria `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="7b09e-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b09e-115">Embora não seja recomendado em um ambiente de produção, você pode testar um arquivo de configuração localizado em um compartilhamento de arquivos não HTTPS usando a configuração do registro EnableSIPHighSecurityMode para desabilitar o modo de alta segurança SIP no cliente.</span><span class="sxs-lookup"><span data-stu-id="7b09e-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="7b09e-116">Em seguida, você pode usar a configuração do registro CustomStateURL para especificar um local não HTTPS para o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="7b09e-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="7b09e-117">Observe que o Lync 2013 homenageia as configurações do registro do Lync 2010, mas o hive do registro foi atualizado.</span><span class="sxs-lookup"><span data-stu-id="7b09e-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="7b09e-118">Você criaria as configurações do registro da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7b09e-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7b09e-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="7b09e-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="7b09e-120">Tipo: DWORD</span><span class="sxs-lookup"><span data-stu-id="7b09e-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="7b09e-121">Dados do valor: 0</span><span class="sxs-lookup"><span data-stu-id="7b09e-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="7b09e-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="7b09e-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="7b09e-123">Tipo: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="7b09e-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="7b09e-124">Dados de valor (exemplos):\\file://lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="7b09e-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="7b09e-125">Localize o estado de presença personalizado especificando um ou mais esquemas de ID de localidade (LCID) no arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="7b09e-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="7b09e-126">O exemplo mais adiante neste tópico mostra a localização em inglês-Estados Unidos (1033), norueguês-Bokmål (1044), francês-França (1036) e Turco (1055).</span><span class="sxs-lookup"><span data-stu-id="7b09e-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="7b09e-127">Para obter uma lista de LCIDs, consulte IDs de localidade atribuídas <http://go.microsoft.com/fwlink/p/?linkid=157331>pela Microsoft em.</span><span class="sxs-lookup"><span data-stu-id="7b09e-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="7b09e-128">Para adicionar Estados de presença personalizada ao Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7b09e-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="7b09e-129">Crie um arquivo de configuração XML que use o formato do seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b09e-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="7b09e-130">Salve o arquivo de configuração XML em um servidor Web com HTTPS habilitado.</span><span class="sxs-lookup"><span data-stu-id="7b09e-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="7b09e-131">Neste exemplo, o arquivo é chamado Presence. xml e salvo no local https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span><span class="sxs-lookup"><span data-stu-id="7b09e-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="7b09e-132">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7b09e-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="7b09e-133">No Shell de gerenciamento do Lync Server, defina o local do arquivo de configuração XML usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b09e-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="7b09e-134">Use o cmdlet **Grant-CSClientPolicy** para atribuir essa nova política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="7b09e-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="7b09e-135">Para obter detalhes, consulte [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b09e-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="7b09e-136">Por padrão, o Lync Server&nbsp;2013 atualiza as políticas e as configurações do cliente a cada três horas.</span><span class="sxs-lookup"><span data-stu-id="7b09e-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="7b09e-137">Se você quiser continuar a usar as configurações de política de grupo de versões anteriores, como o CustomStateURL, o Lync 2013 reconhecerá as configurações se elas estiverem localizadas no novo hive do registro de política (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="7b09e-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="7b09e-138">No entanto, as políticas de cliente baseadas em servidor têm precedência.</span><span class="sxs-lookup"><span data-stu-id="7b09e-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

