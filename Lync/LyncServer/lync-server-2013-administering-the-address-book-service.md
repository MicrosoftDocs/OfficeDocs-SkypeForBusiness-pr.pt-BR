---
title: 'Lync Server 2013: administrar o serviço de catálogo de endereços'
description: 'Lync Server 2013: administrar o serviço de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86d549b06b5c6ac1c450edf9e7edb0b902ef9adf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552997"
---
# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="2cb9d-103">Administrar o serviço de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb9d-103">Administering the Address Book Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cb9d-104">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2cb9d-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2cb9d-105">Como parte da implantação do Lync Server, Enterprise Edition ou do servidor Standard Edition, o serviço de catálogo de endereços é instalado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-105">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="2cb9d-106">O banco de dados usado pelo serviço de catálogo de endereços – RTCab – é criado no SQL Server (para Enterprise Edition, esse é o servidor back-end do SQL Server; para o servidor Standard Edition, o SQL Server posicionado).</span><span class="sxs-lookup"><span data-stu-id="2cb9d-106">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cb9d-107">Para obter informações sobre como usar o <STRONG>ADSI Edit</STRONG> para editar atributos de objeto dos serviços de domínio do Active Directory, consulte <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-107">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="2cb9d-108">Para obter informações sobre uma ferramenta no kit de recursos especificamente para o serviço de catálogo de endereços, consulte <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-108">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="2cb9d-109">Normalização de Número de Telefone do Servidor de Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="2cb9d-109">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="2cb9d-110">O Lync Server requer números de telefone padrão RFC 3966/E. 164.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-110">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="2cb9d-111">Para usar números de telefone não estruturados ou formatados inconsistentes, o Lync Server depende do servidor de catálogo de endereços para preprocessar números de telefone antes que eles sejam enviados para as regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-111">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="2cb9d-112">Quando um número de telefone é usado no catálogo de endereços e a regra de normalização é aplicada, os clientes, como o Lync Phone Edition e o Lync Mobile, podem usar esses números normalizados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-112">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="2cb9d-p104">As regras de normalização que foram usadas nas versões anteriores podem não funcionar corretamente sem alguns ajustes. Como o espaço em branco e os caracteres não obrigatórios são removidos antes das regras de normalização, se sua expressão regex estiver procurando especificamente por um traço ou outro caractere que foi removido, a regra de normalização pode falhar. Você deve examinar as regras de normalização para verificar se elas não estão procurando por esses caracteres não obrigatórios, ou se a regra pode falhar normalmente e continuar com o evento onde a regra prevê que o caractere estaria presente mas não está.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="2cb9d-116">Replicador de Usuários e Servidor de Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="2cb9d-116">User Replicator and Address Book Server</span></span>

<span data-ttu-id="2cb9d-117">O servidor de catálogo de endereços usa os dados fornecidos pelo Replicator de usuários para atualizar as informações que ele obtém inicialmente da lista de endereços global (GAL).</span><span class="sxs-lookup"><span data-stu-id="2cb9d-117">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="2cb9d-118">O replicador de usuários grava os atributos de serviços de domínio do Active Directory para cada usuário, contato e grupo na tabela AbUserEntry no banco de dados e o servidor do catálogo de endereços sincroniza os dados do usuário do banco de dados em arquivos no repositório de arquivos do servidor do catálogo de endereços e no banco de dados do catálogo de endereços do RTCab.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-118">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="2cb9d-119">O esquema da tabela de AbUserEntry usa duas colunas,   **UserGuid** e **UserData**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-119">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="2cb9d-120">**Userguid** é a coluna de índice e contém o GUID de 16 bytes do objeto do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-120">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="2cb9d-121">**UserData** é uma coluna de imagem que contém todos os atributos de serviços de domínio do Active Directory mencionados anteriormente para esse contato.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-121">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="2cb9d-122">O replicador de usuários determina quais atributos do Active Directory serão gravados lendo uma tabela de configuração localizada na mesma instância baseada no SQL Server que a tabela AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-122">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="2cb9d-123">A tabela AbAttribute tem três colunas, **ID**, **Nome**, **Sinalizadores** e **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-123">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="2cb9d-124">A tabela é criada durante a instalação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-124">The table is created during database setup.</span></span> <span data-ttu-id="2cb9d-125">Se a tabela AbAttribute está vazia, o Replicador de usuários ignora a lógica de processamento da tabela AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-125">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="2cb9d-126">Os atributos do servidor de catálogo de endereços são dinâmicos e recuperados da tabela AbAttribute, que inicialmente é gravada pelo servidor de catálogo de endereços quando o servidor de catálogo de endereços é ativado.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-126">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="2cb9d-127">A ativação do servidor de catálogo de endereços preenche a tabela AbAttribute com os valores mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-127">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cb9d-128">ID</span><span class="sxs-lookup"><span data-stu-id="2cb9d-128">ID</span></span></th>
<th><span data-ttu-id="2cb9d-129">Nome</span><span class="sxs-lookup"><span data-stu-id="2cb9d-129">Name</span></span></th>
<th><span data-ttu-id="2cb9d-130">Sinalizadores</span><span class="sxs-lookup"><span data-stu-id="2cb9d-130">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-131">1</span><span class="sxs-lookup"><span data-stu-id="2cb9d-131">1</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-132">givenName</span><span class="sxs-lookup"><span data-stu-id="2cb9d-132">givenName</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-133">0x01400000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-133">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-134">duas</span><span class="sxs-lookup"><span data-stu-id="2cb9d-134">2</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-135">SN</span><span class="sxs-lookup"><span data-stu-id="2cb9d-135">Sn</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-136">0x02400000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-136">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-137">3D</span><span class="sxs-lookup"><span data-stu-id="2cb9d-137">3</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-138">displayName</span><span class="sxs-lookup"><span data-stu-id="2cb9d-138">displayName</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-139">0x03420000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-139">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-140">4 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-140">4</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-141">Título</span><span class="sxs-lookup"><span data-stu-id="2cb9d-141">Title</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-142">0x04000000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-142">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-143">5 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-143">5</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-144">mailNickname</span><span class="sxs-lookup"><span data-stu-id="2cb9d-144">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-145">0x05400000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-145">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-146">6 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-146">6</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-147">Empresa</span><span class="sxs-lookup"><span data-stu-id="2cb9d-147">Company</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-148">0x06000000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-148">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-149">7 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-149">7</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-150">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="2cb9d-150">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-151">0x07000000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-151">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-152">8 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-152">8</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-153">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="2cb9d-153">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-154">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="2cb9d-154">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-155">9 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-155">9</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-156">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="2cb9d-156">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-157">0x09022800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-157">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-158">10 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-158">10</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-159">homePhone</span><span class="sxs-lookup"><span data-stu-id="2cb9d-159">homePhone</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-160">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-160">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-161">11</span><span class="sxs-lookup"><span data-stu-id="2cb9d-161">11</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-162">Mobile</span><span class="sxs-lookup"><span data-stu-id="2cb9d-162">Mobile</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-163">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-163">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-164">12 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-164">12</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-165">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="2cb9d-165">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-166">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-166">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-167">13 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-167">13</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-168">ipPhone</span><span class="sxs-lookup"><span data-stu-id="2cb9d-168">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-169">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-169">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-170">14 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-170">14</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-171">Email</span><span class="sxs-lookup"><span data-stu-id="2cb9d-171">Mail</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-172">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-172">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-173">15 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-173">15</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-174">groupType</span><span class="sxs-lookup"><span data-stu-id="2cb9d-174">groupType</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-175">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-175">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-176">16 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-176">16</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-177">Department</span><span class="sxs-lookup"><span data-stu-id="2cb9d-177">Department</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-178">0x10000000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-178">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-179">17 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-179">17</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-180">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cb9d-180">Description</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-181">0x11000100</span><span class="sxs-lookup"><span data-stu-id="2cb9d-181">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-182">18 </span><span class="sxs-lookup"><span data-stu-id="2cb9d-182">18</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-183">Manager</span><span class="sxs-lookup"><span data-stu-id="2cb9d-183">Manager</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-184">0x12040001</span><span class="sxs-lookup"><span data-stu-id="2cb9d-184">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-185">19</span><span class="sxs-lookup"><span data-stu-id="2cb9d-185">19</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-186">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="2cb9d-186">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-187">0x00500105</span><span class="sxs-lookup"><span data-stu-id="2cb9d-187">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-188">508</span><span class="sxs-lookup"><span data-stu-id="2cb9d-188">20</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-189">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="2cb9d-189">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-190">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="2cb9d-190">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-191">99</span><span class="sxs-lookup"><span data-stu-id="2cb9d-191">99</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-192">entryID</span><span class="sxs-lookup"><span data-stu-id="2cb9d-192">entryID</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-193">0x99000000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-193">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2cb9d-194">Os números na coluna **ID** devem ser exclusivos e nunca devem ser reutilizados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-194">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="2cb9d-195">Além disso, manter os valores de ID em 256 poupa espaço nos arquivos de saída gravados pelo servidor do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-195">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="2cb9d-196">No entanto, o valor de ID máximo é 65535.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-196">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="2cb9d-197">A coluna **nome** corresponde ao nome do atributo do Active Directory que o replicador de usuário deve colocar na tabela AbUserEntry para cada contato.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-197">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="2cb9d-198">O valor na coluna **sinalizadores** é usado para definir o tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-198">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="2cb9d-199">Os seguintes tipos de atributos de servidor do catálogo de endereços são reconhecidos pelo replicador de usuários, indicado pelo byte inferior do valor na coluna **sinalizadores** .</span><span class="sxs-lookup"><span data-stu-id="2cb9d-199">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cb9d-200">Atributo</span><span class="sxs-lookup"><span data-stu-id="2cb9d-200">Attribute</span></span></th>
<th><span data-ttu-id="2cb9d-201">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cb9d-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-202">0x0</span><span class="sxs-lookup"><span data-stu-id="2cb9d-202">0x0</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p108">Um atributo de seqüência de caracteres. O Replicador de usuário converte esse tipo em UTF-8 antes de armazená-lo na tabela AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-205">0x1</span><span class="sxs-lookup"><span data-stu-id="2cb9d-205">0x1</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p109">Um atributo binário. O Replicador de usuário armazena esse blob sem qualquer conversão.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-208">0x2</span><span class="sxs-lookup"><span data-stu-id="2cb9d-208">0x2</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-209">Um atributo de cadeia de caracteres, mas é incluído apenas se o valor do atributo começa com &quot; Tel: &quot; .</span><span class="sxs-lookup"><span data-stu-id="2cb9d-209">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="2cb9d-210">Isso é principalmente para atributos com valores múltiplos, especificamente <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-210">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="2cb9d-211">Nesse caso, o servidor de catálogo de endereços está interessado apenas em entradas de <strong>proxyAddresses</strong> que começam com &quot; Tel: &quot; .</span><span class="sxs-lookup"><span data-stu-id="2cb9d-211">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="2cb9d-212">Portanto, com o intuito de economizar espaço, o replicador de usuários armazena apenas as entradas que começam com &quot; Tel: &quot; .</span><span class="sxs-lookup"><span data-stu-id="2cb9d-212">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-213">0x3</span><span class="sxs-lookup"><span data-stu-id="2cb9d-213">0x3</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p111">Um atributo de sequência de caracteres booliano, que se for VERDADEIRO faz com que o Replicador de usuário não inclua esse contato na tabela AbUserEntry. Se for FALSO, faz com que o Replicador de usuário inclua os atributos desse contato na tabela AbUserEntry, mas não o atributo específico com esse sinalizador. Este é outro tipo de caso especial que é principalmente para o atributo de <strong>msExchHideFromAddressLists</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-217">0x4</span><span class="sxs-lookup"><span data-stu-id="2cb9d-217">0x4</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-218">Um atributo de cadeia de caracteres, mas é incluído apenas se o valor do atributo começa com &quot; SMTP: &quot; e inclui o &quot; @ &quot; símbolo.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-218">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-219">0x5</span><span class="sxs-lookup"><span data-stu-id="2cb9d-219">0x5</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-220">Um atributo de cadeia de caracteres, mas é incluído apenas se o valor do atributo começa com &quot; Tel: &quot; ou &quot; SMTP: &quot; e inclui o &quot; @ &quot; símbolo.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-220">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-221">0x100</span><span class="sxs-lookup"><span data-stu-id="2cb9d-221">0x100</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-222">Se definido, é um atributo de valores múltiplos que pode aparecer mais de uma vez para cada contato.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-222">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-223">0x400</span><span class="sxs-lookup"><span data-stu-id="2cb9d-223">0x400</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p112">Se definido, identifica o atributo de nome de conta de usuário do email de um contato. O servidor de catálogo de endereços usa esse sinalizador para identificar que valor de atributo mostrar na entrada do log de eventos de normalização do telefone.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-226">0x800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-226">0x800</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p113">Se definido, identifica um atributo necessário para um contato. O servidor de catálogo de endereços inclui um usuário na tabela AbUserEntry somente se houver um valor para este atributo em Active Directory. Se houver mais de um atributo obrigatório, somente é necessário que um deles tenha que incluir o usuário em um valor na tabela AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-230">0x1000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-230">0x1000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-231">Se definido, o servidor de catálogo de endereços sempre normaliza o valor desse atributo.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-231">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-232">0x2000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-232">0x2000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-233">Se definido, o servidor de catálogo de endereços usa o número normalizado de <strong>proxyAddresses</strong>, se a configuração de CMS do <strong>UseNormalizationRules</strong> é FALSO; caso contrário, ele se comporta igual a quando o bit de sinalizador é 0x1000.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-233">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-234">0x4000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-234">0x4000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p114">Se definido, o servidor de catálogo de endereços não inclui os objetos que têm esse valor para o atributo especificado na tabela AbUserEntry. Por exemplo, se o atributo <strong>msRTCSIP-PrimaryUserAddress</strong> tem esse bit de sinalizador definido, os contatos que tenham esse atributo não são gravados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-237">0x8000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-237">0x8000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p115">Se definido, o servidor de catálogo de endereços não inclui objetos na tabela AbUserEntry que não possuam esse valor para o atributo especificado. Se os bits de sinalizador 0x4000 e 0x8000 são definidos em um objeto, o atributo com o valor de bit de sinalizador definido como 0x4000 terá precedência e o objeto é excluído da tabela AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-240">0x10000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-240">0x10000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p116">Se definido, representa um objeto de grupo. O Replicador de usuário usa esse bit de sinalizador para incluir os contatos com o  atributo de <strong>groupType</strong> cuja presença indica um grupo (por exemplo, uma lista de distribuição ou um grupo de segurança).</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-243">0x20000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-243">0x20000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-244">Se definido, o Replicador de usuário usa esse bit de sinalizador para incluir este atributo em arquivos de servidor de catálogo de endereços específicos de dispositivo (ou seja, arquivos com uma extensão .dabs).</span><span class="sxs-lookup"><span data-stu-id="2cb9d-244">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2cb9d-245">Nas versões anteriores do Lync Server, ao aplicar uma alteração no Active Directory, o administrador seria necessário para executar **Update-CSUserDatabase** e **Update – CSAddressBook** Windows PowerShell cmdlets para persistir a alteração para o banco de dados de usuário do Lync Server e para o banco de dados do RTCab imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-245">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="2cb9d-246">No Lync Server 2013, o replicador de usuários do Lync Server selecionará as alterações do Active Directory e atualizará o banco de dados de usuário do Lync Server com base em um intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-246">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="2cb9d-247">O replicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-247">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="2cb9d-248">Se a consulta web ao Catálogo de Endereços estiver habilitada, as mudanças serão refletidas nos resultados de busca por clientes Lync.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-248">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="2cb9d-249">Os administradores precisarão executar o Atualizar -CSAddressBook somente se o download de arquivo do Catálogo de Endereços estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-249">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cb9d-250">Por padrão, o replicador de usuários do Lync Server é executado automaticamente a cada 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-250">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="2cb9d-251">Você pode configurar esse intervalo usando o set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt; .</span><span class="sxs-lookup"><span data-stu-id="2cb9d-251">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="2cb9d-252">Filtrando o catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="2cb9d-252">Filtering the Address Book</span></span>

<span data-ttu-id="2cb9d-253">Os usuários preenchidos nos arquivos do servidor do catálogo de endereços podem ser controlados com base em determinados atributos dos serviços de domínio do Active Directory listados na tabela AbAttribute.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-253">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="2cb9d-254">Um desses atributos que é usado para a filtragem é o atributo do **msExchangeHideFromAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-254">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="2cb9d-255">Este é um atributo de usuário adicionado pelo esquema do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-255">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="2cb9d-256">Se o valor desse atributo é VERDADEIRO, o Exchange Server usa esse atributo para ocultar o contato da lista de endereços global do Outlook (GAL).</span><span class="sxs-lookup"><span data-stu-id="2cb9d-256">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="2cb9d-257">Da mesma forma, se o valor desse atributo é VERDADEIRO, o Replicador de usuário não inclui o usuário na tabela AbUserEntry e esse usuário não estará nos arquivos do servidor de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-257">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="2cb9d-p120">Você pode usar alguns bits de sinalizadores para definir um filtro a ser usado nos atributos do servidor de catálogo de endereços. Por exemplo, a presença de determinados bits de sinalizador pode identificar um atributo como um atributo de inclusão ou exclusão. O Replicador de usuários filtra os contactos que contêm um atributo de exclusão e filtra conteúdos que não têm um atributo de inclusão.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2cb9d-261">Para obter mais informações sobre como filtrar o catálogo de endereços, consulte <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlets do servidor do catálogo de endereços no Lync Server 2013</A>e <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filtrar catálogo de endereços do Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="2cb9d-261">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="2cb9d-p121">Atualmente existem três filtros diferentes. A tabela a seguir lista esses filtros.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cb9d-264">Atributo</span><span class="sxs-lookup"><span data-stu-id="2cb9d-264">Attribute</span></span></th>
<th><span data-ttu-id="2cb9d-265">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cb9d-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-266">0x800</span><span class="sxs-lookup"><span data-stu-id="2cb9d-266">0x800</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p122">Se definido, identifica um atributo necessário para um contato. O Replicador de usuário usa esse bit de sinalizador para filtrar os contatos que não contêm pelo menos um atributo necessário. O OuPathId é um atributo obrigatório, que sempre é definido. Portanto, pelo menos um dos outros necessários atributos devem ser definidos. Caso contrário, o contato (isto é, com valor do atributo OuPathId necessário) ainda não será gravado no banco de dados. Por exemplo, se <strong>telephoneNumber</strong> e <strong>TelefoneResidencial</strong> são definidos como atributos necessários, somente os contatos que têm pelo menos um desses atributos são gravados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb9d-273">0x4000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-273">0x4000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p123">Se definido, identifica um atributo de exclusão. O Replicador de usuário usa esse bit de sinalizador para filtrar os contactos que contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> é definido como um atributo de exclusão, contatos que têm este atributo não são gravados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb9d-277">0x8000</span><span class="sxs-lookup"><span data-stu-id="2cb9d-277">0x8000</span></span></p></td>
<td><p><span data-ttu-id="2cb9d-p124">Se definido, identifica um atributo de inclusão. O Replicador de usuário usa esse bit de sinalizador para filtrar os contactos que não contêm esse atributo. Por exemplo, se <strong>msRTCSIP-PrimaryUserAddress</strong> é definido como um atributo de inclusão, somente os contatos que têm este atributo são gravados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2cb9d-281">Se os bits de sinalizador 0x4000 (excluir atributo) e 0x8000 (incluir atributo) estão definidos, o bit 0x4000 substitui o bit 0x8000 e o contato é excluído.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-281">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="2cb9d-p125">Embora você possa filtrar o catálogo de endereços para incluir somente certos usuários, limitar as entradas não limita a capacidade de  outros usuários para entrar em contato com os usuários filtrados ou para ver seu status de presença. Os usuários sempre podem enviar manualmente mensagens instantâneas, iniciar chamadas ou encontrar os usuários que não estão no catálogo de endereços, digitando o nome completo de entrada de um usuário. Além disso, as informações de contato para um usuário também podem ser encontradas no Outlook.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="2cb9d-285">Enquanto os registros de contato completo nos arquivos do catálogo de endereços permitem que você use o Lync Server para iniciar chamadas de email, telefone ou Enterprise Voice (ou seja, se o Enterprise Voice estiver habilitado no servidor) com usuários que não estão configurados para o protocolo SIP, algumas organizações preferem incluir apenas usuários habilitados para SIP nas entradas do servidor do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-285">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="2cb9d-286">Você pode filtrar o catálogo de endereços para incluir somente os usuários habilitados para o SIP limpando o bit 0x800 na coluna **Sinalizadores** dos seguintes atributos obrigatórios: **mailNickname**, **telephoneNumber**, **homePhone** e **celular**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-286">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="2cb9d-287">Você também pode filtrar o catálogo de endereços para incluir somente os usuários habilitados para SIP, definindo o 0x8000 (inclua o atributo) na coluna \*\*Sinalizadores \*\* do atributo \*\*msRTCSIP-PrimaryUserAddress \*\*.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-287">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="2cb9d-288">Isso também ajuda a excluir as contas de serviço de arquivos de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-288">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="2cb9d-289">Depois de modificar a tabela AbAttribute, você pode atualizar os dados na tabela AbUserEntry executando o comando do cmdlet **Update-CsUserDatabase**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-289">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="2cb9d-290">Após a conclusão da replicação UR, é possível atualizar o arquivo no repositório de arquivos do servidor de catálogo de endereços manualmente, executando o comando cmdlet **UpdateCsAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-290">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cb9d-291">O servidor front-end no qual o servidor do catálogo de endereços é colocado não é administrativamente configurável.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-291">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="2cb9d-292">Um é escolhido durante a implantação — normalmente, o primeiro servidor front-end implantado.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-292">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="2cb9d-293">No caso de falha, o serviço de catálogo de endereços mudará para outro servidor de front-end e não exigirá atenção administrativa.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-293">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cb9d-294">Se você consolidou ou modificou sua infraestrutura de uma implantação de várias florestas ou de uma implantação pai/filho (como consolidar sua infraestrutura antes de migrar para o Lync Server), você pode descobrir que o download do serviço de catálogo de endereços e a consulta à Web do catálogo de endereços falham para alguns usuários.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-294">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="2cb9d-295">Quando em uma implantação que tinha vários domínios ou florestas, o atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> é preenchido nos objetos de usuário que estão apresentando o problema.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-295">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="2cb9d-296">O atributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> deve ser definido como NULO nesses objetos para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="2cb9d-296">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

