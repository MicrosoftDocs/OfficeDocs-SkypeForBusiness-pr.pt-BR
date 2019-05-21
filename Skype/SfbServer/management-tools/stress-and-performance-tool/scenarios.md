---
title: Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o teste de desempenho e carga, usando a ferramenta stress and performance.
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299380"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015
 
Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer o teste de desempenho e carga, usando a ferramenta stress and performance.
  
Para executar a ferramenta de stress and performance do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve primeiro ser configurada para cenários relevantes para você. Se o Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, a simulação de carga provavelmente falhará. Com a ferramenta de stress e desempenho do Skype for Business Server 2015, estamos fornecendo exemplos de scripts do Shell de gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367). Elas podem ser usadas como um ponto de partida para configurar a implantação do Skype for Business Server. Este artigo descreve os exemplos do Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 em geral, temos outros tópicos de planejamento e implantação para isso. Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de gerenciamento do Skype for Business Server em inserir introdução aqui. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre como executar scripts do Shell de gerenciamento do Skype for Business Server

Estamos fornecendo exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga. Como esses scripts são destinados à simulação de carga, você os encontrará como simples e permissivos. Isso pode não ser adequado para o seu ambiente de produção. Reembolsamos que esses scripts são exemplos, você precisará examiná-los e, em muitos casos, fazer alterações pertinentes ao seu ambiente antes de poder usá-los de forma prática. No mínimo, esperamos que você precise modificar o script de grupo de serviços de resposta (RSG) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agente). Mas você não precisa executá-lo, se não precisar.
  
> [!CAUTION]
> Tome cuidado ao revisar e compreender esses exemplos. Os scripts substituirão as configurações existentes na topologia quando forem executados. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomes de versão de cliente de ferramenta de stress e desempenho

Talvez seja necessário configurar a política de verificação de versão do cliente se você tiver alterado anteriormente as configurações dos valores padrão. Se você não tiver certeza sobre isso, verifique a [documentação da verificação de versão do cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
A ferramenta stress and Performance usa as seguintes versões de agente de usuário por padrão ao se comunicar com o Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (ferramenta de stress e desempenho do Skype for Business Server 2015)
    
- OCPHONE/.0.522
    
Para o cliente Mobility (UCWA) no LyncPerfTool:
  
- Ferramenta perf UCWA/Web Conference
    
- Ferramenta perf UCWA/móvel
    

