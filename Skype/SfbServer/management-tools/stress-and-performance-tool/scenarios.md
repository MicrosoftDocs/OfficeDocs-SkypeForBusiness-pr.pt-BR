---
title: Cenários de desempenho da ferramenta de estresse e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o desempenho e testar a carga, usando a ferramenta de estresse e desempenho.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983846"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho da ferramenta de estresse e desempenho do Skype for Business Server 2015
 
Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o desempenho e testar a carga, usando a ferramenta de estresse e desempenho.
  
Para executar a ferramenta de estresse e desempenho do Skype for Business Server 2015 (LyncPerfTool), a topologia 2015 do Skype for Business Server deve primeiro ser configurada para cenários relevantes. Se o Skype for Business Server 2015 não estiver configurado ou configurado incorretamente, sua simulação de carga provavelmente falhará. Com a ferramenta de estresse e desempenho do Skype for Business Server 2015, estamos fornecendo exemplos de scripts do Shell de gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367). Eles podem ser usados como um ponto de partida para configurar sua implantação do Skype for Business Server. Este artigo descreve os exemplos do Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 geralmente, temos outros tópicos de planejamento e implantação para isso. Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de gerenciamento do Skype for Business Server em inserir introdução aqui. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre a execução de scripts do Shell de gerenciamento do Skype for Business Server

Estamos fornecendo exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga. Como esses scripts se destinam à simulação de carga, você vai encontrá-los simples e permissivos. Isso pode não ser apropriado para seu ambiente de produção. Mais uma vez, enfatizamos que esses scripts são exemplos, você precisará examiná-los e, em muitos casos, fazer alterações relevantes para seu ambiente antes de poder usá-las de forma prática. No mínimo, esperamos que você precise modificar o script de grupo de serviço de resposta (RSG) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agentes). Mas você não precisa executar isso, se não for necessário.
  
> [!CAUTION]
> Tome cuidado ao examinar e compreender esses exemplos. Os scripts substituirão as configurações existentes na topologia quando forem executados. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomes de versão de cliente da ferramenta de estresse e desempenho

Talvez seja necessário configurar a política de verificação de versão do cliente se você tiver alterado anteriormente as configurações dos valores padrão. Se você não tiver certeza sobre isso, verifique a [documentação de verificação da versão do cliente](https://msdn.microsoft.com/vsto/jj923060).
  
A ferramenta de estresse e desempenho usa as seguintes versões de agente de usuário por padrão ao se comunicar com o Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 estresse e ferramenta de desempenho)
    
- OCPHONE/.0.522
    
Para o cliente de mobilidade (UCWA) no LyncPerfTool:
  
- Ferramenta de perf UCWA/conferência da Web
    
- Ferramenta UCWA perf/móvel
    

