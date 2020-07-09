---
title: Criar um mapa de construção para o painel de qualidade de chamada (CQD)
ms.author: lolaj
author: LolaJacobsen
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
description: Saiba como criar um mapa de construção que você pode usar para carregar locatários e construir dados no painel de qualidade de chamada (CQD).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085998"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Criar um mapa de construção para o painel de qualidade de chamada (CQD)

Em uma implantação do Microsoft Teams ou do Skype for Business Online, todos os clientes são externos. Como resultado, por padrão, todos os clientes são relatados como externos no painel de qualidade de chamada (CQD), independentemente de o cliente estar conectado a uma rede corporativa interna.

Ao trabalhar com o CQD, você precisa saber a localização de um ponto de extremidade e se ele está conectado a uma rede que você pode gerenciar ou uma rede que não pode gerenciar, a pressuposição é que você só pode melhorar as redes que você pode gerenciar. Ao carregar as informações de sub-rede e de construção no CQD, você habilita o CQD para determinar se o ponto de extremidade foi conectado a uma rede interna (gerenciada) ou a uma rede externa (não gerenciada). É por isso que é importante criar um mapa de construção para sua organização e [carregá-lo no CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Ferramentas de mapeamento de construção

Há muitas maneiras de mapear as sub-redes da sua organização. Se precisar de ajuda, você pode usar o módulo do PowerShell CQDTools descrito nesta [postagem de blog](https://aka.ms/cqdtools). Essas ferramentas se baseiam no PowerShell e usam sites e serviços do Active Directory (AD) e os serviços DHCP da Microsoft para ajudar a preencher previamente o seu arquivo de construção. Essas ferramentas ajudarão nas seguintes tarefas:

1. Consultar sites e serviços de anúncios e criar um arquivo de construção com base nas informações contidas em.
1. Consulta um servidor ou servidores DHCP da Microsoft para extrair informações de sub-rede e criar automaticamente um arquivo de construção.
1. Valide um arquivo de construção existente, verificando se há duplicatas e sobrepostas.
1. Localizar sub-redes não mapeadas no CQD.

## <a name="related-topics"></a>Tópicos relacionados

[Carregar o locatário e compilar dados no CQD](CQD-upload-tenant-building-data.md)