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
# <a name="acquiring-a-location-in-lync-server-2013"></a>Adquirindo um local no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

Em uma implantação do Lync Server 2013 E9-1-1, cada cliente Lync ou Lync Phone Edition conectado internamente adquire ativamente seu próprio local. Após o registro SIP, o cliente fornece todas as informações de conectividade de rede que ele conhece em uma solicitação de local para o serviço de informações de local, que é um serviço Web apoiado por um banco de dados do SQL Server replicado. Cada pool de site central tem um serviço de informações de local, que usa as informações de rede para consultar seus registros em busca de um local correspondente. Se houver uma correspondência, o serviço de informações de local retornará um local ao cliente. Se não houver uma correspondentes, pode ser solicitado que o usuário insira uma localização manualmente (dependendo das definições da política de localização). Os dados de localização são transmitidos de volta para o cliente em um formato XML padronizado da IETF (Internet Engineering Task Force) chamado de PIDF-LO (Objeto de Local de Formato de Dados de Informação de Presença).

O cliente do Lync Server inclui os dados do PIDF-LO como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviço E9-1-1 para determinar o PSAP apropriado e encaminhar a chamada para esse PSAP junto com o ESQK correto, que permite ao dispatcher do PSAP obter o local do chamador.

O diagrama a seguir mostra como um cliente do Lync Server adquire um local (exceto para o método de local com base no endereço MAC do cliente de terceiros):

![Como o cliente adquire um diagrama de local](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Como o cliente adquire um diagrama de local")

Para um cliente adquirir uma localização, as seguintes etapas devem ser executadas:

1.  O administrador preenche o banco de dados do serviço de informações de local com o wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para locais de resposta de emergência correspondentes (ERLs)).

2.  Se você usar um provedor de serviço E9-1-1 por tronco SIP, o administrador validará as partes do endereço residencial dos ERLs com um banco de dados MSAG (Guia principal de endereços de ruas) mantido pelo provedor de serviço E9-1-1. Se você usar um gateway ELIN, o administrador garantirá que a operadora da PSTN carregue os ELINs no banco de dados ALI (Identificação de local automática).

3.  Durante o registro ou sempre que uma alteração na rede ocorrer, um cliente conectado internamente enviará uma solicitação de local que contém os endereços de rede descobertos do cliente para o serviço de informações de local.

4.  O serviço de informações de local consulta seus registros publicados em busca de um local e, se uma correspondência for encontrada, retorna o ERL ao cliente no formato PIDF-LO.

</div>

<span> </span>

</div>

</div>

</div>

