---
title: Visão geral da implantação para o sistema de sala do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: Leia sobre como implantar o sistema de sala do Skype, uma reunião solução de sala consiste em integrada de hardware e software que é otimizado para ingressar Skype para reuniões de negócios.
ms.openlocfilehash: 94a9b1cb7ff3f341a51944cdc678bc66e44831cb
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699314"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>Planejamento da implantação do sistema de sala do Skype em Skype para negócios
 
Leia sobre como implantar o sistema de sala do Skype, uma reunião solução de sala consiste em integrada de hardware e software que é otimizado para ingressar Skype para reuniões de negócios.
  
> [!NOTE]
> Para os fins deste conteúdo, Skype for Business para sistema de sala inteligente, Crestron RL, e Polycom CX8000 vai ser referida como sistema de sala Skype. 

> [!NOTE]
> Sistemas de sala Skype v2 é um produto diferente com diferentes dependências e procedimentos de implantação. Para obter informações sobre os sistemas de sala Skype v2, consulte [Planejar sistemas de sala Skype v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).
  
 Sistema de sala do Skype é um Skype para o cliente de comunicação unificada de negócios que foi otimizada para Skype para reuniões de negócios em salas de conferência físico.
  
Cliente do sistema de sala Skype desenvolvido do Skype para o cliente de negócios usando o Skype para negócios SDK. O Skype para o cliente de negócios é executado em segundo plano no modo de interface do usuário suprimida parcial. O Skype para o cliente de negócios controla a Galeria de vídeo e o estágio de conteúdo na tela à frente da sala. Cliente do sistema de sala Skype fornece uma experiência de console a exibição de table-top para controlar as reuniões. Sistema de sala Skype fornece: 
  
- Experiência de participação da reunião com um toque
    
- Instalação automática da galeria de vídeo com várias exibições 
    
- Painel habilitado para toque na frente da tela da sala 
    
- Integração de calendário para acesso às reuniões programadas
    
- Troca e compartilhamento de conteúdo 
    
Este documento orienta você durante o provisionamento de sistema de sala do Skype em Skype para Business Server e o Exchange Server. Consulte também o guia de instalação de sistema do Skype sala fornecido pelo administrador, que orienta você Configurando o aparelho de PC e dispositivos na sala de reunião. 
  
## <a name="prerequisites"></a>Pré-requisitos

A seguir estão os requisitos de sistema do Skype sala: 
  
- Uma conta de caixa de correio de recursos do Exchange para facilitar o agendamento do calendário para as salas de reunião com serviço de Descoberta Automática habilitado no Exchange Server (2013 preferencial).
    
- Um Skype para conta de sistema de sala do Skype Business habilitado em um Skype para pool de servidores de negócios (Enterprise ou Standard Edition).
    
- Um aparelho do cliente de sistema de sala Skype PC com o software necessário instalado. O PC deve estar executando o sistema operacional padrão do Windows 7 Incorporado. Esse hardware é fornecida pelo parceiros de OEM junto com todos os dispositivos (exibições, câmera, microfone, alto-falantes).
    
- Se você decidir ingressar o aparelho de sistema de sala Skype PC em um domínio do Active Directory Domain Services (AD DS), você deve especificar as configurações de diretiva de grupo que não interferir no sistema de sala Skype. Como alternativa, você pode deixar este PC no grupo de trabalho. 
    
- Os direitos de usuário apropriados para executar os cmdlets especificados neste documento. Os cmdlets CsMeetingRoom são modelado de acordo com o cmdlet CsUser. Portanto, todas as funções de controle de acesso baseadas em função (RBAC) necessárias para executar os cmdlets CsUser também se aplicam aos cmdlets CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologias suportadas

A tabela a seguir indica a interoperabilidade do cliente do sistema de sala Skype entre várias implantações do Skype para topologias de negócios e do Exchange, no local ou na nuvem: 
  

|**Topologia**|**AD**|**Skype for Business**|**Exchange**|
|:-----|:-----|:-----|:-----|
|No local  <br/> |No local  <br/> |No local  <br/> |No local  <br/> |
|O Office 365 multilocatário (O365MT)  <br/> |Online  <br/> |Online  <br/> |Online  <br/> |
|Office 365 dedicado  <br/> (Entre em contato com seu provedor de serviços)  <br/> |No local  <br/> |Online  <br/> |Online  <br/> |
|Híbrido (domínio dividido)  <br/> Sem suporte  <br/> |No local  <br/> No local  <br/> No local  <br/> |No local  <br/> Online  <br/> Online  <br/> |Online  <br/> Online  <br/> No local  <br/> |
   
Versões anteriores ao Lync Server 2013 são parcialmente suportado. Nesses cenários, o sistema de sala Skype podem participar de Skype para conferências de negócios (aqueles que estão agendadas por usuários hospedados no Lync Server 2010) desde que as conferências são "públicas", o que significa que as conferências não são personalizado para acesso restrito. 
  
Sistema de sala Skype não podem ser hospedado em uma versão do Lync server anteriores ao Lync Server 2013. Quando um sistema de sala Skype não pode se conectar ao Exchange para recuperar as configurações de calendário-- por exemplo, quando não há nenhuma caixa de correio do Exchange configurada para a conta do sistema de sala Skype ou não pode ser acessado Exchange – reunir agora e conferência ad-hoc funcionará, mas ingressando em uma não irá reunião agendada. 
  
A tabela a seguir indica o suporte de cliente do sistema do Skype sala com versões do Exchange Server: 
  

|**Exchange**|**No local**|**Online**|**Híbrido**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Sim (floresta única apenas)  <br/> |N/D  <br/> |N/D  <br/> |
|Exchange 2013  <br/> |Sim (suporte a várias florestas disponível para Exchange 2013 CU6 e versões mais recentes)  <br/> |Sim  <br/> |Sim  <br/> |
|Exchange 2016  <br/> |Sim (multi floresta suporte disponível)  <br/> |Sim  <br/> |Sim  <br/> |
   

