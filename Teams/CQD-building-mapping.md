---
title: Criar um mapa de construção para o Painel de Qualidade de Chamada (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como criar um mapa de construção que você pode usar para carregar locatários e criar dados no Painel de Qualidade de Chamada (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584030"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Criar um mapa de construção para o Painel de Qualidade de Chamada (CQD)

Em uma Microsoft Teams ou Skype for Business Online, todos os clientes são externos. Como resultado, por padrão, todos os clientes são relatados como externos no Painel de Qualidade de Chamada (CQD), independentemente de o cliente estar conectado em uma rede corporativa interna.

Ao trabalhar com o CQD, você precisa saber o local de um ponto de extremidade e se ele estava conectado a uma rede que você pode gerenciar ou uma rede que não pode gerenciar, pressuprindo que você só pode melhorar as redes que você pode gerenciar. Ao carregar a sub-rede e criar informações para o CQD, você habilita o CQD para determinar se o ponto de extremidade estava conectado a uma rede interna (gerenciada) ou a uma rede externa (não gerenciada). É por isso que é importante criar um mapa de construção para sua organização e [enviá-lo para o CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Criar ferramentas de mapeamento

Há muitas maneiras de mapear as sub-redes da sua organização. Se precisar de ajuda, você pode usar o Módulo do PowerShell do CQDTools descrito nesta [postagem de blog.](https://aka.ms/cqdtools) Essas ferramentas se baseiam no PowerShell e usam Sites e Serviços do Active Directory (AD) e serviços DHCP da Microsoft para ajudar a preencher previamente seu arquivo de construção. Essas ferramentas ajudarão com as seguintes tarefas:

1. Consultar Sites e Serviços do AD e criar um arquivo de construção com base nas informações contidas.
1. Consultar um servidor DHCP da Microsoft ou servidores para obter informações de sub-rede e criar automaticamente um arquivo de construção.
1. Validar um arquivo de construção existente, verificando se há duplicatas e sobreposições.
1. Encontre sub-redes não mapeadas no CQD.

## <a name="related-topics"></a>Tópicos relacionados

[Upload locatário e a criação de dados no CQD](CQD-upload-tenant-building-data.md)