---
title: Requisitos do cliente Windows e suporte de software
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumo: revise os requisitos de suporte ao cliente do Windows ao planejar o Skype for Business Server.'
ms.openlocfilehash: a66887b616461a40c6326a66d982a8bfbe8e9605
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803481"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos do cliente Windows e suporte de software
 
**Resumo:** Examine os requisitos de suporte ao cliente do Windows ao planejar o Skype for Business Server.
  
Esta seção resume o software necessário para dar suporte aos clientes do Windows do Skype for Business.  Esses clientes são instalados quando o Office 365 é instalado e também estão disponíveis no artigo [baixar o Skype for Business em todos os seus dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> O suplemento de reunião online do Skype for Business, que dá suporte ao gerenciamento de reuniões dentro do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Skype for Business. 
  
**Software necessário para o cliente Skype for Business e o suplemento de reunião online**

|**Componente do sistema**|**Versões com suporte**|
|:-----|:-----|
|Sistema operacional Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operacional Windows 7  <br/> Windows Server 2008 R2 ou posterior com Service Pack mais recente  <br/> **Observação:** O Skype for Business e o suplemento de reunião online para Skype for Business não são compatíveis com o Windows Vista ou Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador da Internet do Internet Explorer 11  <br/>  Internet Explorer 10 navegador da Internet <br/> Navegador da Internet do Internet Explorer 9  <br/> Navegador da Internet do Internet Explorer 8  <br/> Navegador da Internet do Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/>  Navegador Google Chrome na Web  <br/>**Observação:** Se você estiver usando o Skype for Business com o Microsoft Exchange Online e a sua organização tiver implantado um proxy HTTP de autenticação, é preciso ter o Internet Explorer 8 ou posterior.           |
|Integração com o Microsoft Office  <br/> | Outlook 2010 ou posterior |
|Integração com o Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte os [requisitos do sistema](https://products.office.com/en-us/office-system-requirements) do Office 365 para o hardware necessário para executar o cliente Skype for Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicativo reuniões do Skype e Skype for Business Web App 

O aplicativo reuniões do Skype e o Skype for Business Web App dão suporte a combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [planejar clientes de reuniões (aplicativo Web e aplicativo reuniões)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você pretende usar os recursos de conferência do Skype for Business, evite usar os perfis obrigatórios dos serviços de domínio Active Directory para se conectar ao cliente Skype for Business. Como perfis obrigatórios são perfis de usuário somente leitura, as chaves de infraestrutura de chave pública (PKI) necessárias para a conferência do Skype for Business não podem ser salvas no perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>System requirements for Skype for Business for Windows Phone
 
 
O Microsoft Skype for Business para Windows Phone fornece mensagens instantâneas (IM), presença avançada e telefonia para os usuários de sua organização que estão se conectando de um smartphone ou um dispositivo móvel com Windows Professional. Os dispositivos móveis permitem que os usuários estendam o alcance do Skype for Business. Este tópico descreve as considerações de planejamento para o Skype for Business para Windows Phone que incluem a identificação de pré-requisitos e requisitos técnicos, componentes obrigatórios e diretrizes de implantação.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Pré-requisitos do Skype for Business para Windows Phone

Veja a seguir os pré-requisitos do Skype for Business para Windows Phone.
  
- Windows Phone 8.1 ou posterior.
    
- O dispositivo com Windows Phone precisa ter as atualizações mais recentes disponíveis na Microsoft. Para obter detalhes, consulte a seção Windows Phone 8,1 no [histórico de atualização do Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- O dispositivo precisa ter 22 MB de espaço em disco disponível.
    
- O usuário precisa ter um plano de dados e voz para uma operadora.


## <a name="see-also"></a>Confira também

[Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)](meetings-clients.md)
  
[Requisitos do cliente Skype for Business no Mac](mac-requirements.md)

[Baixe o Skype for Business em todos os seus dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos do sistema do Office 365](https://products.office.com/en-us/office-system-requirements)
