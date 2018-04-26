---
title: Implantar Sistema de Salas do Skype no Skype for Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: Leia sobre como implantar o , uma solução para sala de reunião que consiste em hardware e software integrados e otimizados para ingressar em reuniões do .
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a>Implantar Sistema de Salas do Skype no Skype for Business Server
 
Leia sobre como implantar o , uma solução para sala de reunião que consiste em hardware e software integrados e otimizados para ingressar em reuniões do .
  
> [!NOTE]
> Para as finalidades deste conteúdo, o  para SMART Room System, Crestron RL e Polycom CX8000 serão conhecidos como . 
  
 Skype Room System is a Skype for Business unified communications client that has been optimized for Skype for Business meetings in physical conference rooms.
  
The Skype Room System client was developed from the Skype for Business client by using the Skype for Business SDK. O cliente  é executado em segundo plano no modo suprimido de UI parcial. O cliente  controla a galeria de vídeo e o estágio do conteúdo na tela da frente da sala. O cliente  fornece uma experiência de console na exibição de mesa para controlar as reuniões. Sistema de Salas do Skype 
  
- Experiência de participação da reunião com um toque
    
- Instalação automática da galeria de vídeo com várias exibições 
    
- Painel habilitado para toque na frente da tela da sala 
    
- Integração de calendário para acesso às reuniões programadas
    
- Troca e compartilhamento de conteúdo 
    
This document guides you through provisioning Skype Room System in Skype for Business Server and Exchange Server. Consulte também o Guia de Instalação do  fornecido pelo administrador, que orienta você durante a configuração do PC e dispositivos na sala de reunião. 
  
## <a name="prerequisites"></a>Pré-requisitos

Following are the requirements for Skype Room System: 
  
- Uma conta de caixa de correio de recursos do Exchange para facilitar o agendamento do calendário para as salas de reunião com serviço de Descoberta Automática habilitado no Exchange Server (2013 preferencial).
    
- A Skype for Business-enabled Skype Room System account on a Skype for Business Server pool (Enterprise or Standard Edition).
    
- Um PC do cliente  com todos os softwares exigidos instalados. O PC deve estar executando o sistema operacional padrão do Windows 7 Incorporado. Esse hardware é fornecida pelo parceiros de OEM junto com todos os dispositivos (exibições, câmera, microfone, alto-falantes).
    
- Se você decidir colocar o PC do  em um domínio de Serviços de Domínio do Active Directory (AD DS), você deve especificar as configurações de política de grupo que não interferem com . Como alternativa, você pode deixar este PC no grupo de trabalho. 
    
- Os direitos de usuário apropriados para executar os cmdlets especificados neste documento. Os cmdlets CsMeetingRoom são modelado de acordo com o cmdlet CsUser. Portanto, todas as funções de controle de acesso baseadas em função (RBAC) necessárias para executar os cmdlets CsUser também se aplicam aos cmdlets CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologias suportadas

A tabela a seguir indica a interoperabilidade do cliente  entre várias implantações das topologias do  e do Exchange, no local ou na nuvem: 
  

|**Topologia**|**AD**|**Skype for Business**|**Exchange**|
|:-----|:-----|:-----|:-----|
|No local  <br/> |No local  <br/> |No local  <br/> |No local  <br/> |
|Office 365 Multi-tenant (O365MT)  <br/> |Online  <br/> |Online  <br/> |Online  <br/> |
|Office 365 dedicado  <br/> Contato com seu provedor de serviço  <br/> |No local  <br/> |Online  <br/> |Online  <br/> |
|Híbrido (domínio dividido)  <br/> Sem suporte  <br/> |No local  <br/> No local  <br/> No local  <br/> |No local  <br/> Online  <br/> Online  <br/> |Online  <br/> Online  <br/> No local  <br/> |
   
Versões anteriores ao Lync Server 2013 são parcialmente suportado. Nesses cenários, o  pode participar nas conferências do  (aquelas agendadas pelos usuários hospedados no Lync Server 2010) contanto que as conferências sejam "públicas", indicando que o as conferências não são personalizadas para acesso restrito. 
  
O  não pode ser hospedado em um Lync server versão anterior à Lync Server 2013. Quando um  não pode se conectar ao Exchange para recuperar as configurações do calendário, por exemplo, quando não há caixa de correio do Exchange configurada para a conta do  ou o Exchange não pode ser acessado -- a conferência Reunir Agora e ad hoc funcionará, mas o ingresso em uma reunião agendada não. 
  
A tabela a seguir indica a suportabilidade do cliente  com as versões do Exchange Server: 
  

|**Exchange**|**No local**|**Online**|**Híbrido**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Sim (floresta única apenas)  <br/> |N/D  <br/> |N/D  <br/> |
|Exchange 2013  <br/> |Sim (suporte a várias florestas disponível para Exchange 2013 CU6 e versões mais recentes)  <br/> |Sim  <br/> |Sim  <br/> |
|Exchange 2016  <br/> |Yes (multi forest support available)  <br/> |Sim  <br/> |Sim  <br/> |
   

