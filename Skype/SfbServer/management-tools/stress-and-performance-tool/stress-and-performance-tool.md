---
title: Ferramenta de desempenho e estresse do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: A Ferramenta de Desempenho e Estresse do Skype for Business Server 2015 é usada durante o planejamento de capacidade e o ajuste de desempenho em ambientes de não produção ou teste.
ms.openlocfilehash: 0ce2c4f4a608f6ecba980d7f8fe77fbc2863d81d
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012365"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Ferramenta de desempenho e estresse do Skype for Business Server 2015
 
A Ferramenta de Desempenho e Estresse do Skype for Business Server 2015 é usada durante o planejamento de capacidade e o ajuste de desempenho em ambientes de não produção ou teste.
  
A Ferramenta de Desempenho e Estresse do Skype for Business Server 2015 inclui ferramentas que simplificarão seu planejamento de capacidade para o Skype for Business Server 2015. A Ferramenta de Desempenho e Estresse do Skype for Business Server 2015 ajudará você a:
  
- Simplificar seu planejamento de hardware para o Skype for Business Server
    
- Dar mais conhecimento e práticas recomendadas para ajuste de desempenho
    
- Medir o desempenho das implantações do Skype for Business Server
    
Normalmente, você usaria essa ferramenta depois de usar a Ferramenta de Planejamento do [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com a Calculadora de Planejamento de Capacidade do Skype for Business Server [2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Essa ferramenta não será atualizada para o Skype for Business Server 2019.
  
## <a name="tests"></a>Testes

A Ferramenta de Estresse e Desempenho pode simular esses tipos de carga do usuário:
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Mensagens Instantâneas (IM) e presença   |Audioconferência   |
|Compartilhamento de aplicativos   |VoIP (Voice over IP), incluindo a simulação de rede telefônica pública comutado (PTSN)   |
|Conferência do Cliente do Web Access   |Atendimento automático de conferência   |
|Grupos de resposta   |Expansão da lista de distribuição   |
|Download do livro de endereços e consulta do livro de endereços   |Chamadas aprimoradas do 911 (E911) e perfil de local (plano de discagem)   |
|MultiView   |Colaboração de dados   |
|Mobilidade   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos na Ferramenta de Desempenho e Estresse do Skype for Business Server 2015

Esses aplicativos fazem parte da Ferramenta de Desempenho e Estresse do Skype for Business Server:
  
|Mal-Intencionado|Descrição|
|:-----|:-----|
|UserProvisioningTool.exe   |Essa ferramenta é usada para criar usuários e contatos.   |
|UserProfileGenerator.exe   |Usado para configurar as características da carga do usuário que você está simulando.   |
|LyncPerfTool.exe   |A ferramenta que simula a carga do usuário.   |
|Default.tmx   |Necessário para usar a Ferramenta de Registro em Log do Skype for Business Server 2015.   |
|Exemplos de script de provisionamento   |Usado para configurar a topologia para a execução de testes de carga, com base em cenários específicos. Você provavelmente precisará modificá-los para torná-los relevantes para seu ambiente específico.   |
   
## <a name="topics-in-this-section"></a>Tópicos nesta seção

Você deve revisar os seguintes artigos se precisar saber mais:
  
- [Pré-requisitos e configuração para a Ferramenta de Desempenho e Estresse do Skype for Busines](prerequisites-and-setup.md)
    
- [Cenários de desempenho para a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015](scenarios.md)
    
  - [Provisionando a topologia para executar a carga em cenários de Estresse e Desempenho](provisioning-the-topology-to-run-load.md)
    
  - [Configurando políticas para a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015](configuring-policies.md)
    
- [Usando a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015](using-the-tool.md)
    
- [Perguntas frequentes sobre a Ferramenta de Desempenho e Estresse do Skype for Business Server 2015](faq.md)
    

