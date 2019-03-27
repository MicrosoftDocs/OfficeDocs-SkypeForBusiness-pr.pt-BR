---
title: Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar Skype para Business 2015 de servidor fazer o desempenho e teste de carga, usando a ferramenta de Stress e desempenho.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874588"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho
 
Tarefas que você precisará fazer para configurar Skype para Business 2015 de servidor fazer o desempenho e teste de carga, usando a ferramenta de Stress e desempenho.
  
Para executar o Skype para Business Server 2015 ferramenta de Stress e desempenho (LyncPerfTool), o Skype para Business Server 2015 topologia deve ser configurada para cenários relevantes para você. Se Skype para Business Server 2015 não estiver configurado ou está configurada incorretamente, sua simulação de carga é bem provável falha. Com o Skype para ferramenta de desempenho e estresse do Business Server 2015, estamos fornecendo exemplo Skype para obter scripts de Shell de gerenciamento do servidor de negócios e arquivos de recursos básicos como parte do de [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367). Essas podem ser usadas como um ponto de partida para configurar sua Skype para implantação de servidor de negócios. Este artigo descreve os exemplos do Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudá-lo a descrevem como configurar o Skype para Business Server 2015 geralmente, temos outros tópicos de planejamento e implantação para que. Para obter detalhes sobre como trabalhar com o Windows PowerShell no Skype para Business Server 2015, consulte o Skype para documentação do Shell de gerenciamento do servidor de negócios em Inserir introdução aqui. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre a execução Skype para gerenciamento de servidor de negócios scripts do shell

Estamos fornecendo scripts do PowerShell de amostra que você pode usar para preparar seus simulações de carga. Porque esses scripts são destinados simulação de carga, você encontrará eles sejam simples e permissivo. Que pode não ser apropriada para seu ambiente de produção. Novamente, podemos sobrecarregar que esses scripts são exemplos, você precisará revisá-las e em muitos casos fazer alterações relevantes ao seu ambiente antes de poder fazer uso prático deles. No mínimo, esperávamos que seria necessário modificar o script de resposta serviço RSG (grupo) com sua topologia em mente (para especificar os operadores atribuídos a grupos de operadores). Mas você não precisa executar que, se você não precisa.
  
> [!CAUTION]
> Por favor, tome cuidado na análise e Noções básicas sobre esses exemplos. Scripts substituirá quaisquer definições existentes na topologia quando executado. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Ferramenta de stress e desempenho nomes de versão de cliente

Você pode precisar configurar a política de verificação de versão do cliente se você alterou anteriormente as configurações dos valores padrão. Se não tiver certeza sobre isso, consulte a [documentação verificar versão do cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
A ferramenta de Stress e desempenho usa as seguintes versões do agente do usuário por padrão durante a comunicação com Skype para Business Server 2015:
  
- LSPT/15.0.0.0 (Skype para Business Server 2015 ferramenta de Stress e desempenho)
    
- OCPHONE/.0.522
    
Para o cliente de mobilidade (UCWA) no LyncPerfTool:
  
- UCWA Perf ferramenta/Webconferência
    
- Ferramenta de Perf UCWA/Mobile
    

