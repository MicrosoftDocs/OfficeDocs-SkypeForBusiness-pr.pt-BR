---
title: Pré-requisitos
description: Pré-requisitos.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560097"
---
# <a name="prerequisites"></a>Pré-requisitos

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-19_

Há vários requisitos de configuração de hardware, software e sistema que você precisará para executar a ferramenta de estresse e desempenho do Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Requisitos de hardware do cliente

Para executar a ferramenta de estresse e desempenho do Lync Server 2013 em sua implantação do Lync Server 2013, para todos os usuários do 4.500 cuja carga você deseja simular, você precisará de pelo menos um computador dedicado que atenda aos seguintes requisitos mínimos de hardware:

  - adaptador de rede de 1 Gigabit

  - 8 GB de RAM

  - 2 unidades de processamento central (CPUs) de núcleo dual

</div>

<div>

## <a name="client-software-requirements"></a>Requisitos de software do cliente

Para executar a ferramenta de estresse e desempenho do Lync Server 2013 em sua implantação do Lync Server 2013, os sistemas operacionais com suporte são:

  - Sistema operacional Windows Server 2012

  - Sistema operacional Windows Server 2008 (edição de 64 bits)

O computador cliente deve atender aos seguintes requisitos de software:

  - Você deve ter o [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime instalado.

  - No Windows Server 2008/Windows Server 2012, o recurso experiência desktop deve estar habilitado.

  - Você deve ter o [pacote redistribuível do Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64) instalado.

  - Uma implantação do Lync Server 2013 totalmente configurada.

<div>


> [!IMPORTANT]  
> Bibliotecas do Microsoft Unified Communications Managed API (UCMA) 4,0 estão incluídas no pacote de instalação, portanto, o UCMA não é necessário e não deve ser instalado em computadores clientes.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Requisitos de configuração

Os computadores que executarão a ferramenta de estresse e desempenho do Lync Server 2013 devem ser configurados de acordo com os seguintes requisitos:

1.  Você deve estar conectado como um membro do domínio ou do grupo Administradores local.

2.  O Lync Server 2013 estresse e a ferramenta de desempenho (LyncPerfTool.exe) não podem ser executados em um computador que também está executando os componentes do Lync Server 2013.

3.  Você deve executar a ferramenta de criação de usuário do Lync Server 2013 (UserProvisioningTool.exe) no servidor de front-end ou no servidor Standard Edition onde as contas de usuário residirão. Quando a ferramenta é executada várias vezes, cada usuário habilitado para a comunicação unificada da Microsoft deve ter um número de telefone exclusivo.

4.  O tamanho do arquivo da página deve ser gerenciado pelo sistema ou deve ser pelo menos 1,5 vezes a quantidade de RAM no sistema.

</div>

</div>

<span> </span>

</div>

</div>

</div>

