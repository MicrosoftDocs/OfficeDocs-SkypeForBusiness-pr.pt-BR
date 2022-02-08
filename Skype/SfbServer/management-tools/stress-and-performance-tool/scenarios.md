---
title: Cenários de desempenho para a ferramenta Skype for Business Server stress e desempenho do 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer testes de desempenho e carga, usando a Ferramenta de Estresse e Desempenho.
ms.openlocfilehash: 3f8818018120a7230bcdaaa9b6cd04009e761640
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390053"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Cenários de desempenho para a ferramenta Skype for Business Server stress e desempenho do 2015
 
Tarefas que você precisará fazer para configurar o Skype for Business Server 2015 para fazer testes de desempenho e carga, usando a Ferramenta de Estresse e Desempenho.
  
Para executar Skype for Business Server ferramenta de desempenho e estresse do Skype for Business Server 2015 (LyncPerfTool), a topologia do Skype for Business Server 2015 deve ser configurada primeiro para cenários relevantes para você. Se Skype for Business Server 2015 não estiver configurado ou estiver configurado incorretamente, sua simulação de carga provavelmente falhará. Com a Skype for Business Server 2015 Stress and Performance Tool, estamos fornecendo exemplos Skype for Business Server scripts do Shell de Gerenciamento e arquivos de recursos básicos como parte do [download da ferramenta](https://www.microsoft.com/download/details.aspx?id=50367). Eles podem ser usados como um ponto de partida para configurar sua implantação Skype for Business Server usuário. Este artigo descreve os exemplos Windows PowerShell fornecidos.
  
> [!NOTE]
> Este tópico não ajudará você a descrever como configurar o Skype for Business Server 2015 geralmente, temos outros tópicos de Planejamento e Implantação para isso. Para obter detalhes sobre como trabalhar com Windows PowerShell no Skype for Business Server 2015, consulte Skype for Business Server documentação do Shell de Gerenciamento em Inserir introdução AQUI. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sobre a execução Skype for Business Server scripts de shell de gerenciamento

Estamos fornecendo exemplos de scripts do PowerShell que você pode usar para se preparar para suas simulações de carga. Como esses scripts se destinam à simulação de carga, você os encontrará simples e permissivos. Isso pode não ser apropriado para seu ambiente de produção. Novamente, enfatizamos que esses scripts são exemplos, você precisará revisá-los e, em muitos casos, fazer alterações relevantes para seu ambiente antes de poder fazer uso prático deles. No mínimo, esperamos que você precise modificar o script RSG (Grupo de Serviços de Resposta) com sua topologia em mente (para especificar os agentes atribuídos aos grupos de agentes). Mas você não precisa executar isso, se não precisar.
  
> [!CAUTION]
> Tenha cuidado ao analisar e compreender esses exemplos. Os scripts substituirão as configurações existentes na topologia quando executados. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nomes de versão do cliente da Ferramenta de Desempenho e Estresse

Talvez seja necessário configurar a política de Verificação de Versão do Cliente se tiver alterado anteriormente as configurações dos valores padrão. Se você não tiver certeza sobre isso, verifique a documentação de Verificação de Versão [do Cliente](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).
  
A Ferramenta de Estresse e Desempenho usa as seguintes versões do Agente de Usuário por padrão ao se comunicar com Skype for Business Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server Ferramenta de Desempenho e Estresse 2015)
    
- OCPHONE/.0.522
    
Para o cliente mobility (UCWA) no LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
