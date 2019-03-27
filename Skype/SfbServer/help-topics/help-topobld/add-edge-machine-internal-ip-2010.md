---
title: Adicionar IP Interno de Máquina de Borda 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.
ms.openlocfilehash: b54fae5ce536e1f859c4c05059b18b5e5067af7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873323"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Adicionar IP Interno de Máquina de Borda 2010

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.

- Em **endereço IPv4 interno**, digite o endereço IP do servidor de borda que você deseja adicionar ao pool.

- Em **FQDN interno**, digite o nome de domínio totalmente qualificado (FQDN) do servidor de borda que você deseja adicionar ao pool.

O FQDN que você especificar deve ser idêntico ao nome do computador que está configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Portanto, você deve configurar um sufixo de sistema de nome de domínio (DNS) no nome do computador para ser implantado como um servidor de borda que não está unido a um domínio. Para obter detalhes sobre como adicionar um sufixo DNS para um nome de computador, consulte [Configurar o DNS para suporte de borda](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


