---
title: Ferramenta de Stress and Performance do Skype for Business Server 2015
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: A Ferramenta de Stress and Performance do Skype for Business Server 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814921"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Ferramenta de Stress and Performance do Skype for Business Server 2015
 
A Ferramenta de Stress and Performance do Skype for Business Server 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.
  
A Ferramenta de Stress and Performance do Skype for Business Server 2015 inclui ferramentas que simplificarão seu planejamento de capacidade para o Skype for Business Server 2015. A Ferramenta de Stress and Performance do Skype for Business Server 2015 ajudará você a:
  
- Simplifique seu planejamento de hardware para o Skype for Business Server
    
- Aumentar o conhecimento e as práticas recomendadas para ajuste de desempenho
    
- Medir o desempenho de suas implantações do Skype for Business Server
    
Normalmente, você usaria essa ferramenta depois de usar a Ferramenta de Planejamento do [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com a Calculadora de Planejamento de Capacidade do Skype for Business Server [2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Essa ferramenta não será atualizada para o Skype for Business Server 2019.
  
## <a name="tests"></a>Testes

A Ferramenta de Stress and Performance pode simular esses tipos de carga de usuário:
  
|||
|:-----|:-----|
|Mensagens instantâneas (IM) e presença  <br/> |Audioconferência  <br/> |
|Compartilhamento de aplicativos  <br/> |Simulação de VoIP (Voz sobre IP), incluindo simulação de PTSN (Rede Telefônica Pública Comucionária)  <br/> |
|Web Access Client conferencing  <br/> |Atendente automático da conferência  <br/> |
|Grupos de resposta  <br/> |Expansão da lista de distribuição  <br/> |
|Download do livro de endereços e consulta do livro de endereços  <br/> |Chamadas aprimoradas do 911 (E911) e perfil de local (plano de discagem)  <br/> |
|MultiView  <br/> |Colaboração de dados  <br/> |
|Mobilidade  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos na Ferramenta de Stress and Performance do Skype for Business Server 2015

Esses aplicativos fazem parte da Ferramenta de Stress and Performance do Skype for Business Server:
  
|**Ferramenta**|**Descrição**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Essa ferramenta é usada para criar usuários e contatos.  <br/> |
|UserProfileGenerator.exe  <br/> |Usado para configurar as características da carga do usuário que você está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |A ferramenta que simula a carga do usuário.  <br/> |
|Default.tmx  <br/> |Necessário para usar a Ferramenta de Log do Skype for Business Server 2015.  <br/> |
|Exemplos de script de provisionamento  <br/> |Usado para configurar a topologia para a execução de testes de carga, com base em cenários específicos. Você provavelmente precisará modificá-los para torná-los relevantes para seu ambiente específico.  <br/> |
   
## <a name="topics-in-this-section"></a>Tópicos nesta seção

Você deve revisar os seguintes artigos se precisar saber mais:
  
- [Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Busines](prerequisites-and-setup.md)
    
- [Cenários de desempenho da Ferramenta de Stress and Performance do Skype for Business Server 2015](scenarios.md)
    
  - [Provisionando a topologia para executar a carga em cenários de Stress and Performance](provisioning-the-topology-to-run-load.md)
    
  - [Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015](configuring-policies.md)
    
- [Usando a Ferramenta de Stress and Performance do Skype for Business Server 2015](using-the-tool.md)
    
- [Perguntas frequentes sobre a Ferramenta de Stress and Performance do Skype for Business Server 2015](faq.md)
    

