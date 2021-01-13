---
title: Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015
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
description: Tarefas que você precisará realizar para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814701"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015
 
Tarefas que você precisará realizar para configurar o Skype for Business Server 2015 para realizar testes de desempenho e carga, usando a Ferramenta de Stress and Performance.
  
Para executar a Ferramenta de Stress and Performance do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve primeiro ser configurada para cenários relevantes para você. Se o Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, sua simulação de carga provavelmente falhará. Com a Ferramenta de Stress and Performance do Skype for Business Server 2015, fornecemos exemplos de scripts do Shell de Gerenciamento do Skype for Business Server e arquivos de recursos básicos como parte do download da [ferramenta.](https://www.microsoft.com/download/details.aspx?id=50367) Eles podem ser usados como ponto de partida para configurar sua implantação do Skype for Business Server. Este artigo descreve os exemplos do Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 em geral, temos outros tópicos de Planejamento e Implantação para isso. Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype for Business Server 2015, consulte a documentação do Shell de Gerenciamento do Skype for Business Server em Inserir introdução AQUI. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre a execução de scripts do shell de gerenciamento do Skype for Business Server

Fornecemos exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga. Como esses scripts se destinam à simulação de carga, você os verá como simples e permissivos. Isso pode não ser apropriado para seu ambiente de produção. Novamente, enfatizamos que esses scripts são exemplos, você precisará revisá-los e, em muitos casos, fazer alterações relevantes para seu ambiente antes de poder usá-los de forma prática. No mínimo, esperamos que você precise modificar o script RSG (Grupo de Serviço de Resposta) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agentes). Mas você não precisa executar isso, se não precisar.
  
> [!CAUTION]
> Tome cuidado ao analisar e entender esses exemplos. Os scripts substituirão quaisquer configurações existentes na topologia quando executados. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomes de versão do cliente da Ferramenta de Stress and Performance

Talvez seja necessário configurar a política de Verificação de Versão do Cliente se tiver alterado anteriormente as configurações dos valores padrão. Se você não tiver certeza sobre isso, verifique a documentação de Verificação [de Versão do Cliente.](https://msdn.microsoft.com/vsto/jj923060)
  
A Ferramenta de Stress and Performance usa as seguintes versões do Agente do Usuário por padrão ao se comunicar com o Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Para o cliente de Mobilidade (UCWA) no LyncPerfTool:
  
- Ferramenta UCWA Perf/Web Conference
    
- Ferramenta UCWA Perf/Mobile
    

