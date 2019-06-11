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

# <a name="acquiring-a-location-in-lync-server-2013"></a>Adquirindo um local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

Em uma implantação do Lync Server 2013 E9-1-1, todos os clientes do Lync ou Lync Phone Edition conectados internamente adquirem ativamente seu próprio local. Após o registro do SIP, o cliente fornece todas as informações de conectividade de rede que ele conhece em si em uma solicitação de localização para o serviço de informações de localização, que é um serviço da Web apoiado por um banco de dados replicado do SQL Server. Cada pool de sites central tem um serviço de informações de localização, que usa as informações de rede para consultar seus registros para um local correspondente. Se houver uma correspondência, o serviço de informações de localização retornará um local ao cliente. Caso contrário, o usuário poderá ser solicitado a inserir o local manualmente (dependendo das configurações de política de local). Os dados do local são transmitidos de volta ao cliente em um formato XML padronizado IETF (Internet Engineering Task Force) chamado PIDF-LO (Presence Information Data Format Location Object).

O cliente do Lync Server inclui os dados do PIDF como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviços E9-1-1 para determinar o PSAP apropriado e direcionar a chamada para esse PSAP juntamente com o ESQK correto, o que permite que o Dispatcher do PSAP obtenha o Localização do chamador.

O diagrama a seguir mostra como um cliente do Lync Server adquire um local (exceto para o método de localização baseada em endereço MAC do cliente de terceiros):

![Como o cliente adquire um diagrama de localização] (images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Como o cliente adquire um diagrama de localização")

Para um cliente adquirir um local, as seguintes etapas devem ser executadas:

1.  O administrador preenche o banco de dados do serviço de informações de localização com o wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para locais de reação de emergência correspondentes (ERLs)).

2.  Se você usar um provedor de serviços E9-1-1 do tronco SIP, o administrador validará as partes de endereço cívico do ERLs em comparação com um banco de dados MSAG (Catálogo de Endereços Principal) mantido pelo provedor do serviços E9-1-1. Se você usar um gateway ELIN, o administrador garante que a operadora de PSTN fará o upload dos ELINs para o banco de dados de Identificação de local automática (ALI).

3.  Durante o registro ou sempre que ocorre uma alteração na rede, um cliente conectado internamente envia uma solicitação de localização que contém os endereços de rede descobertos do cliente para o serviço de informações de localização.

4.  O serviço de informações de localização consulta os registros publicados de um local e, se for encontrada uma coincidência, retorna o ERL para o cliente no formato PIDF-LO.

</div>

<span> </span>

</div>

</div>

</div>

