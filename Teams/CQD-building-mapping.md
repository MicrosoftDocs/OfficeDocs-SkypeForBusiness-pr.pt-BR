---
title: Criar um mapa de construção para o Painel de Qualidade de Chamada (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como criar um mapa de construção que você pode usar para carregar o locatário e criar dados no CQD (Painel de Qualidade de Chamada).
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789816"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Criar um mapa de construção para o Painel de Qualidade de Chamada (CQD)

Em uma implantação do Microsoft Teams ou Skype for Business Online, todos os clientes são externos. Como resultado, por padrão, todos os clientes são relatados como externos no Painel de Qualidade de Chamada (CQD), independentemente de o cliente estar conectado em uma rede corporativa interna.

Ao trabalhar com o CQD, você precisa saber a localização de um ponto de extremidade e se ele estava conectado a uma rede que você pode gerenciar ou uma rede que não pode ser gerenciada, pressupõendo que você só pode melhorar as redes que pode gerenciar. Ao carregar informações de sub-rede e compilar no CQD, você habilita o CQD para determinar se o ponto de extremidade foi conectado a uma rede interna (gerenciada) ou a uma rede externa (não gerenciada). É por isso que é importante criar um mapa de construção para sua organização e [carregá-lo no CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Criando ferramentas de mapeamento

Há muitas maneiras de mapear as sub-redes da sua organização. Se precisar de ajuda, você poderá usar o Módulo CQDTools do PowerShell descrito nesta [postagem no blog](https://aka.ms/cqdtools). Essas ferramentas são baseadas no PowerShell e usam Sites e Serviços do Active Directory (AD) e serviços DHCP da Microsoft para ajudar a preencher previamente o arquivo de construção. Essas ferramentas ajudarão com as seguintes tarefas:

1. Consulte Sites e Serviços do AD e crie um arquivo de construção com base nas informações contidas.
1. Consulte um servidor DHCP da Microsoft ou servidores para efetuar pull de informações de sub-rede e criar automaticamente um arquivo de construção.
1. Valide um arquivo de construção existente, verificando se há duplicatas e sobreposições.
1. Localize sub-redes não mapeadas no CQD.

## <a name="related-topics"></a>Tópicos relacionados

[Carregar dados de locatário e de criação no CQD](CQD-upload-tenant-building-data.md)