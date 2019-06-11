---
title: 'Lync Server 2013: Adquirindo um local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="53a52-102">Adquirindo um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a52-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a52-103">_**Tópico da última modificação:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="53a52-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="53a52-104">Em uma implantação do Lync Server 2013 E9-1-1, todos os clientes do Lync ou Lync Phone Edition conectados internamente adquirem ativamente seu próprio local.</span><span class="sxs-lookup"><span data-stu-id="53a52-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="53a52-105">Após o registro do SIP, o cliente fornece todas as informações de conectividade de rede que ele conhece em si em uma solicitação de localização para o serviço de informações de localização, que é um serviço da Web apoiado por um banco de dados replicado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="53a52-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="53a52-106">Cada pool de sites central tem um serviço de informações de localização, que usa as informações de rede para consultar seus registros para um local correspondente.</span><span class="sxs-lookup"><span data-stu-id="53a52-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="53a52-107">Se houver uma correspondência, o serviço de informações de localização retornará um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="53a52-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="53a52-108">Caso contrário, o usuário poderá ser solicitado a inserir o local manualmente (dependendo das configurações de política de local).</span><span class="sxs-lookup"><span data-stu-id="53a52-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="53a52-109">Os dados do local são transmitidos de volta ao cliente em um formato XML padronizado IETF (Internet Engineering Task Force) chamado PIDF-LO (Presence Information Data Format Location Object).</span><span class="sxs-lookup"><span data-stu-id="53a52-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="53a52-110">O cliente do Lync Server inclui os dados do PIDF como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviços E9-1-1 para determinar o PSAP apropriado e direcionar a chamada para esse PSAP juntamente com o ESQK correto, o que permite que o Dispatcher do PSAP obtenha o Localização do chamador.</span><span class="sxs-lookup"><span data-stu-id="53a52-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="53a52-111">O diagrama a seguir mostra como um cliente do Lync Server adquire um local (exceto para o método de localização baseada em endereço MAC do cliente de terceiros):</span><span class="sxs-lookup"><span data-stu-id="53a52-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="53a52-112">![Como o cliente adquire um diagrama de localização] (images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Como o cliente adquire um diagrama de localização")</span><span class="sxs-lookup"><span data-stu-id="53a52-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="53a52-113">Para um cliente adquirir um local, as seguintes etapas devem ser executadas:</span><span class="sxs-lookup"><span data-stu-id="53a52-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="53a52-114">O administrador preenche o banco de dados do serviço de informações de localização com o wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para locais de reação de emergência correspondentes (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="53a52-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="53a52-p102">Se você usar um provedor de serviços E9-1-1 do tronco SIP, o administrador validará as partes de endereço cívico do ERLs em comparação com um banco de dados MSAG (Catálogo de Endereços Principal) mantido pelo provedor do serviços E9-1-1. Se você usar um gateway ELIN, o administrador garante que a operadora de PSTN fará o upload dos ELINs para o banco de dados de Identificação de local automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="53a52-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="53a52-117">Durante o registro ou sempre que ocorre uma alteração na rede, um cliente conectado internamente envia uma solicitação de localização que contém os endereços de rede descobertos do cliente para o serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="53a52-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="53a52-118">O serviço de informações de localização consulta os registros publicados de um local e, se for encontrada uma coincidência, retorna o ERL para o cliente no formato PIDF-LO.</span><span class="sxs-lookup"><span data-stu-id="53a52-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

