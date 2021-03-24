---
title: Cenários de desempenho para a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Estresse e Desempenho.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105367"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho para a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015
 
Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Estresse e Desempenho.
  
Para executar a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve ser configurada primeiro para cenários relevantes para você. Se o Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, sua simulação de carga provavelmente falhará. Com a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015, estamos fornecendo exemplos de scripts do Shell de Gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do download da [ferramenta.](https://www.microsoft.com/download/details.aspx?id=50367) Eles podem ser usados como ponto de partida para configurar sua implantação do Skype for Business Server. Este artigo descreve os exemplos Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 geralmente, temos outros tópicos de Planejamento e Implantação para isso. Para obter detalhes sobre como trabalhar com Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de Gerenciamento do Skype for Business Server em Inserir introdução AQUI. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre como executar scripts de shell de gerenciamento do Skype for Business Server

Estamos fornecendo exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga. Como esses scripts se destinam à simulação de carga, você os encontrará simples e permissivos. Isso pode não ser apropriado para seu ambiente de produção. Novamente, enfatizamos que esses scripts são exemplos, você precisará revisá-los e, em muitos casos, fazer alterações relevantes para seu ambiente antes de poder fazer uso prático deles. No mínimo, esperamos que você precise modificar o script RSG (Grupo de Serviços de Resposta) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agentes). Mas você não precisa executar isso, se não precisar.
  
> [!CAUTION]
> Tenha cuidado ao analisar e compreender esses exemplos. Os scripts substituirão as configurações existentes na topologia quando executados. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomes de versão do cliente da Ferramenta de Desempenho e Estresse

Talvez seja necessário configurar a política de Verificação de Versão do Cliente se tiver alterado anteriormente as configurações dos valores padrão. Se você não tiver certeza sobre isso, verifique a documentação de Verificação de Versão [do Cliente](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
A Ferramenta de Estresse e Desempenho usa as seguintes versões do Agente de Usuário por padrão ao se comunicar com o Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Para o cliente mobility (UCWA) no LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
