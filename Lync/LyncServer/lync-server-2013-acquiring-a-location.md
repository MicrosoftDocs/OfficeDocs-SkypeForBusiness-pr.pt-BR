---
title: 'Lync Server 2013: adquirindo um local'
description: 'Lync Server 2013: aquisição de um local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571107"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="d1a12-103">Adquirindo um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1a12-103">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1a12-104">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="d1a12-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="d1a12-105">Em uma implantação do Lync Server 2013 E9-1-1, cada cliente Lync ou Lync Phone Edition conectado internamente adquire ativamente seu próprio local.</span><span class="sxs-lookup"><span data-stu-id="d1a12-105">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="d1a12-106">Após o registro SIP, o cliente fornece todas as informações de conectividade de rede que ele conhece em uma solicitação de local para o serviço de informações de local, que é um serviço Web apoiado por um banco de dados do SQL Server replicado.</span><span class="sxs-lookup"><span data-stu-id="d1a12-106">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="d1a12-107">Cada pool de site central tem um serviço de informações de local, que usa as informações de rede para consultar seus registros em busca de um local correspondente.</span><span class="sxs-lookup"><span data-stu-id="d1a12-107">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="d1a12-108">Se houver uma correspondência, o serviço de informações de local retornará um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="d1a12-108">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="d1a12-109">Se não houver uma correspondentes, pode ser solicitado que o usuário insira uma localização manualmente (dependendo das definições da política de localização).</span><span class="sxs-lookup"><span data-stu-id="d1a12-109">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="d1a12-110">Os dados de localização são transmitidos de volta para o cliente em um formato XML padronizado da IETF (Internet Engineering Task Force) chamado de PIDF-LO (Objeto de Local de Formato de Dados de Informação de Presença).</span><span class="sxs-lookup"><span data-stu-id="d1a12-110">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="d1a12-111">O cliente do Lync Server inclui os dados do PIDF-LO como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviço E9-1-1 para determinar o PSAP apropriado e encaminhar a chamada para esse PSAP junto com o ESQK correto, que permite ao dispatcher do PSAP obter o local do chamador.</span><span class="sxs-lookup"><span data-stu-id="d1a12-111">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="d1a12-112">O diagrama a seguir mostra como um cliente do Lync Server adquire um local (exceto para o método de local com base no endereço MAC do cliente de terceiros):</span><span class="sxs-lookup"><span data-stu-id="d1a12-112">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="d1a12-113">![Como o cliente adquire um diagrama de local](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Como o cliente adquire um diagrama de local")</span><span class="sxs-lookup"><span data-stu-id="d1a12-113">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="d1a12-114">Para um cliente adquirir uma localização, as seguintes etapas devem ser executadas:</span><span class="sxs-lookup"><span data-stu-id="d1a12-114">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="d1a12-115">O administrador preenche o banco de dados do serviço de informações de local com o wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para locais de resposta de emergência correspondentes (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="d1a12-115">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="d1a12-p102">Se você usar um provedor de serviço E9-1-1 por tronco SIP, o administrador validará as partes do endereço residencial dos ERLs com um banco de dados MSAG (Guia principal de endereços de ruas) mantido pelo provedor de serviço E9-1-1. Se você usar um gateway ELIN, o administrador garantirá que a operadora da PSTN carregue os ELINs no banco de dados ALI (Identificação de local automática).</span><span class="sxs-lookup"><span data-stu-id="d1a12-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="d1a12-118">Durante o registro ou sempre que uma alteração na rede ocorrer, um cliente conectado internamente enviará uma solicitação de local que contém os endereços de rede descobertos do cliente para o serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="d1a12-118">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="d1a12-119">O serviço de informações de local consulta seus registros publicados em busca de um local e, se uma correspondência for encontrada, retorna o ERL ao cliente no formato PIDF-LO.</span><span class="sxs-lookup"><span data-stu-id="d1a12-119">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

