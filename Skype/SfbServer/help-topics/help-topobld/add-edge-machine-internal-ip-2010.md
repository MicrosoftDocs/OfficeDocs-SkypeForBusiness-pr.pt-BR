---
title: Adicionar IP Interno de Máquina de Borda 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.
ms.openlocfilehash: eb5d2d8aa7dd0d7827e13089f7588f5090b6744a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828781"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Adicionar IP Interno de Máquina de Borda 2010

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.

- No **endereço IPv4 interno,** digite o endereço IP do Servidor de Borda que você deseja adicionar ao pool.

- No **FQDN Interno,** digite o FQDN (nome de domínio totalmente qualificado) do Servidor de Borda que você deseja adicionar ao pool.

O FQDN especificado precisa ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, é necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda que não faz parte de um domínio. Para obter detalhes sobre como adicionar um sufixo DNS ao nome de um computador, consulte [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).


