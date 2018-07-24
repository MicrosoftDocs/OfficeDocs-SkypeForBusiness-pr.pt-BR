---
title: Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: O Skype para ferramenta de desempenho e estresse do Business Server 2015 é usado durante o planejamento de capacidade e ajuste em ambientes de não-produção ou de teste de desempenho.
ms.openlocfilehash: 9ccd4b851ad64f829a15bd6138764995f789dbf6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984460"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype para Business Server 2015 ferramenta de Stress e desempenho
 
O Skype para ferramenta de desempenho e estresse do Business Server 2015 é usado durante o planejamento de capacidade e ajuste em ambientes de não-produção ou de teste de desempenho.
  
O Skype para ferramenta de desempenho e estresse do Business Server 2015 inclui ferramentas que simplificarão seu planejamento de capacidade do Skype para Business Server 2015. O Skype para ferramenta de desempenho e estresse do Business Server 2015 ajudará você a:
  
- Simplificar seu hardware planejando Skype para Business Server
    
- Dar conhecimento é aumentada e práticas recomendadas para ajuste de desempenho
    
- Medir o desempenho do seu Skype para implantações de servidor de negócios
    
Normalmente você usaria esta ferramenta depois de usar o [Skype para ferramenta de planejamento do Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinando a topologia com o [Skype para Calculadora de planejamento de capacidade do Business Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Essa ferramenta não será atualizada para Skype para Business Server 2019.
  
## <a name="tests"></a>Testes

A ferramenta de Stress e desempenho podem simular esses tipos de carga de usuário:
  
|||
|:-----|:-----|
|Instant Messaging (IM) e presença  <br/> |Serviços de audioconferência  <br/> |
|Compartilhamento de aplicativos  <br/> |Simulação (PTSN) de voz sobre IP (VoIP), incluindo a rede telefônica pública comutada  <br/> |
|Webconferência de acesso para cliente  <br/> |Atendedor automático de conferência  <br/> |
|Grupos de resposta  <br/> |Expansão de lista de distribuição  <br/> |
|Download do catálogo de endereços e consulta de catálogo de endereços  <br/> |Enhanced nas 911 chamadas (E911) e o perfil de local (plano de discagem)  <br/> |
|MultiView  <br/> |Colaboração de dados  <br/> |
|Mobilidade  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos com o Skype para Business Server 2015 ferramenta de Stress e desempenho

Esses aplicativos são parte do Skype para ferramenta de desempenho e estresse do Business Server:
  
|**Ferramenta**|**Descrição**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Essa ferramenta é usada para criar usuários e contatos.  <br/> |
|UserProfileGenerator.exe  <br/> |Usado para configurar as características da carga de usuário que você está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |A ferramenta que simula a carga de usuários.  <br/> |
|Default.tmx  <br/> |Necessário para usar o Skype para ferramenta de log do Business Server 2015.  <br/> |
|Exemplos de scripts de provisionamento  <br/> |Usado para configurar a topologia para executar testes de carga, com base em cenários específicos. Você provavelmente precisará modificá-los para que sejam relevantes para seu ambiente específico.  <br/> |
   
## <a name="topics-in-this-section"></a>Tópicos desta seção

Se você precisa saber mais, você deve examinar os seguintes artigos:
  
- [Pré-requisitos e configuração da Ferramenta de Stress and Performance do Skype for Business](prerequisites-and-setup.md)
    
- [Cenários de desempenho para o Skype para Business Server 2015 ferramenta de Stress e desempenho](scenarios.md)
    
  - [Provisionamento a topologia para executar a carga em cenários de Stress e desempenho](provisioning-the-topology-to-run-load.md)
    
  - [Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho](configuring-policies.md)
    
- [Usando o Skype para Business Server 2015 ferramenta de Stress e desempenho](using-the-tool.md)
    
- [Perguntas frequentes para o Skype para Business Server 2015 ferramenta de Stress e desempenho](faq.md)
    

