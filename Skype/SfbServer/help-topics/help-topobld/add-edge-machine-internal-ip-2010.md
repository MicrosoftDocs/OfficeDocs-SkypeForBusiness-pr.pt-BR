---
title: Adicionar IP Interno de Máquina de Borda 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno para o servidor de borda.
ms.openlocfilehash: 1847362f93c1d1ff67c09fb9f552641b0e770bbc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821133"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Adicionar IP Interno de Máquina de Borda 2010

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno para o servidor de borda.

- Em **endereço IPv4 interno**, digite o endereço IP do servidor de borda que você deseja adicionar ao pool.

- Em **FQDN interno**, digite o nome de domínio totalmente qualificado (FQDN) do servidor de borda que você deseja adicionar ao pool.

O FQDN que você especificar deve ser idêntico ao nome do computador que está configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Portanto, você deve configurar um sufixo DNS (sistema de nomes de domínio) no nome do computador a ser implantado como um servidor de borda que não está associado a um domínio. Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte [Configurar o DNS para suporte a Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


