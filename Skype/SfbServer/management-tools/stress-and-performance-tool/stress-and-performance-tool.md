---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: A ferramenta de stress e desempenho do Skype for Business Server 2015 é usada durante o planejamento da capacidade e o ajuste de desempenho em ambientes que não sejam de produção ou de teste.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816150"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
A ferramenta de stress e desempenho do Skype for Business Server 2015 é usada durante o planejamento da capacidade e o ajuste de desempenho em ambientes que não sejam de produção ou de teste.
  
A ferramenta de stress e desempenho do Skype for Business Server 2015 inclui ferramentas que simplificarão o planejamento de capacidade para o Skype for Business Server 2015. A ferramenta de stress e desempenho do Skype for Business Server 2015 ajudará você a:
  
- Simplifique seu planejamento de hardware para o Skype for Business Server
    
- Fornecer conhecimento e práticas recomendadas para ajuste de desempenho
    
- Medir o desempenho de suas implantações do Skype for Business Server
    
Normalmente, você usaria essa ferramenta depois de usar a [ferramenta de planejamento do Skype for Business server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com a [calculadora do planejamento de capacidade do 2015 do Skype for Business Server](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Esta ferramenta não será atualizada para o Skype for Business Server 2019.
  
## <a name="tests"></a>Testes

A ferramenta stress and Performance pode simular esses tipos de carga de usuário:
  
|||
|:-----|:-----|
|Mensagens instantâneas (IM) e presença  <br/> |Audioconferência  <br/> |
|Compartilhamento de aplicativos  <br/> |Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PTSN)  <br/> |
|Conferência de cliente de acesso Web  <br/> |Atendedor automático da conferência  <br/> |
|Grupos de resposta  <br/> |Expansão da lista de distribuição  <br/> |
|Consulta de download e catálogo de endereços do catálogo de endereços  <br/> |Chamadas avançadas de 911 (E911) e perfil de local (plano de discagem)  <br/> |
|Múltipla  <br/> |Colaboração de dados  <br/> |
|Mobilidade  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos na ferramenta de stress e desempenho do Skype for Business Server 2015

Esses aplicativos fazem parte da ferramenta de stress e desempenho do Skype for Business Server:
  
|**Ferramentas**|**Descrição**|
|:-----|:-----|
|UserProvisioningTool. exe  <br/> |Esta ferramenta é usada para criar usuários e contatos.  <br/> |
|UserProfileGenerator. exe  <br/> |Usado para configurar as características da carga de usuário que você está simulando.  <br/> |
|LyncPerfTool. exe  <br/> |A ferramenta que simula a carga do usuário.  <br/> |
|Default. TMX  <br/> |Obrigatório para usar a ferramenta de log do Skype for Business Server 2015.  <br/> |
|Exemplos de script de provisionamento  <br/> |Usado para configurar a topologia para executar testes de carga com base em cenários específicos. Você provavelmente precisará modificá-los para torná-los relevantes para o seu ambiente específico.  <br/> |
   
## <a name="topics-in-this-section"></a>Tópicos desta seção

Você deve revisar os artigos a seguir se precisar saber mais:
  
- [Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business](prerequisites-and-setup.md)
    
- [Cenários de desempenho da ferramenta de stress e desempenho do Skype for Business Server 2015](scenarios.md)
    
  - [Provisionando a topologia para executar carga em cenários de carga e desempenho](provisioning-the-topology-to-run-load.md)
    
  - [Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015](configuring-policies.md)
    
- [Usando a ferramenta de stress e desempenho do Skype for Business Server 2015](using-the-tool.md)
    
- [Perguntas frequentes sobre a ferramenta de stress e desempenho do Skype for Business Server 2015](faq.md)
    

