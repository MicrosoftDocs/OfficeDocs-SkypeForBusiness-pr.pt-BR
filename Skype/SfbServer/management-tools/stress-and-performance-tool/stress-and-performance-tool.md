---
title: Skype for Business Server ferramenta de desempenho e estresse de 2015
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
description: A Skype for Business Server ferramenta de desempenho e estresse 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.
ms.openlocfilehash: 381e6178994ce8d4ce2f3558bd075cf6fc3b6d43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611890"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server ferramenta de desempenho e estresse de 2015
 
A Skype for Business Server ferramenta de desempenho e estresse 2015 é usada durante o planejamento de capacidade e ajuste de desempenho em ambientes de não produção ou teste.
  
A Skype for Business Server ferramenta de desempenho e estresse 2015 inclui ferramentas que simplificarão seu planejamento de capacidade para Skype for Business Server 2015. A Skype for Business Server ferramenta de desempenho e estresse do 2015 ajudará você a:
  
- Simplifique seu planejamento de hardware para Skype for Business Server
    
- Dar mais conhecimento e práticas recomendadas para ajuste de desempenho
    
- Medir o desempenho de suas Skype for Business Server implantações
    
Normalmente, você usaria essa ferramenta depois de usar Skype for Business Server Ferramenta de Planejamento do [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para projetar a topologia e refinar a topologia com Skype for Business Server Calculadora de Planejamento de Capacidade do [Skype for Business Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Esta ferramenta não será atualizada para Skype for Business Server 2019.
  
## <a name="tests"></a>Testes

A Ferramenta de Estresse e Desempenho pode simular esses tipos de carga do usuário:
  
|||
|:-----|:-----|
|Mensagens Instantâneas (IM) e presença  <br/> |Audioconferência  <br/> |
|Compartilhamento de aplicativos  <br/> |VoIP (Voice over IP), incluindo a simulação de rede telefônica pública comutado (PTSN)  <br/> |
|Conferência do Cliente do Web Access  <br/> |Atendimento automático de conferência  <br/> |
|Grupos de resposta  <br/> |Expansão da lista de distribuição  <br/> |
|Download do livro de endereços e consulta do livro de endereços  <br/> |Chamadas aprimoradas do 911 (E911) e perfil de local (plano de discagem)  <br/> |
|MultiView  <br/> |Colaboração de dados  <br/> |
|Mobilidade  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos na ferramenta Skype for Business Server 2015 Stress and Performance Tool

Esses aplicativos fazem parte da ferramenta Skype for Business Server Stress and Performance:
  
|**Ferramenta**|**Descrição**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Essa ferramenta é usada para criar usuários e contatos.  <br/> |
|UserProfileGenerator.exe  <br/> |Usado para configurar as características da carga do usuário que você está simulando.  <br/> |
|LyncPerfTool.exe  <br/> |A ferramenta que simula a carga do usuário.  <br/> |
|Default.tmx  <br/> |Necessário para usar a Ferramenta de Registro em Log Skype for Business Server 2015.  <br/> |
|Exemplos de script de provisionamento  <br/> |Usado para configurar a topologia para a execução de testes de carga, com base em cenários específicos. Você provavelmente precisará modificá-los para torná-los relevantes para seu ambiente específico.  <br/> |
   
## <a name="topics-in-this-section"></a>Tópicos nesta seção

Você deve revisar os seguintes artigos se precisar saber mais:
  
- [Pré-requisitos e configuração para o Skype para Ferramenta de Desempenho e Estresse de Barramentos](prerequisites-and-setup.md)
    
- [Cenários de desempenho para a ferramenta Skype for Business Server stress e desempenho do 2015](scenarios.md)
    
  - [Provisionando a topologia para executar a carga em cenários de Estresse e Desempenho](provisioning-the-topology-to-run-load.md)
    
  - [Configurando políticas para a ferramenta de desempenho e Skype for Business Server 2015](configuring-policies.md)
    
- [Usando a ferramenta Skype for Business Server desempenho e estresse do 2015](using-the-tool.md)
    
- [Perguntas frequentes sobre Skype for Business Server ferramenta de desempenho e estresse de 2015](faq.md)
    

