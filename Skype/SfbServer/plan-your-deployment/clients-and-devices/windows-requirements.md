---
title: Requisitos de cliente do Windows e suporte a software
ms.author: v-cichur
author: cichur
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
description: 'Resumo: revise os requisitos de suporte para cliente do Windows durante o planejamento do Skype for Business Server.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816061"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos de cliente do Windows e suporte a software
 
**Resumo:** Revise os requisitos de suporte para cliente do Windows durante o planejamento do Skype for Business Server.
  
Esta seção resume o software necessário para dar suporte aos clientes Do Windows do Skype for Business. Esses clientes são instalados quando o Microsoft 365 ou Office 365 é instalado e também estão disponíveis em Baixar o Skype for Business em todos os [seus dispositivos.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> O Complemento Reunião Online do Skype for Business, que oferece suporte ao gerenciamento de reuniões de dentro do cliente de colaboração e mensagens do Outlook, é instalado automaticamente com o Skype for Business. 
  
**Software necessário para o cliente Skype for Business e o Complemento reunião online**

|**Componente do sistema**|**Versões com suporte**|
|:-----|:-----|
|Sistema operacional Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou posterior com o service pack mais recente  <br/> **Observação:** O Skype for Business e o Complemento de Reunião Online do Skype for Business não são suportados no Windows Vista ou no Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador Internet Internet Explorer 11  <br/>  Navegador Internet Internet Explorer 10 <br/> Navegador Internet Internet Explorer 9  <br/> Navegador Internet Internet Explorer 8  <br/> Navegador Internet Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/>  Navegador da Web Google Chrome  <br/>**Observação:** Se você estiver usando o Skype for Business com o Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, o Internet Explorer 8 ou posterior será necessário.           |
|Integração com o Microsoft Office  <br/> | Outlook 2010 ou posterior |
|Integração com o Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte os requisitos do Microsoft 365 e do Office [System](https://products.office.com/office-system-requirements) para o hardware necessário para executar o cliente Skype for Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicativo Reuniões do Skype e Skype for Business Web App 

O aplicativo Reuniões do Skype e o Skype for Business Web App suportam combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, [consulte Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você planeja usar os recursos de conferência do Skype for Business, evite usar perfis obrigatórios dos Serviços de Domínio Active Directory para entrar no cliente Skype for Business. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves PKI (infraestrutura de chave pública) necessárias para a conferência do Skype for Business não podem ser salvas no perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos do sistema do Skype for Business para Windows Phone
 
 
O Microsoft Skype for Business para Windows Phone fornece mensagens instantâneas, presença aprimorada e telefonia para usuários em sua organização que estão se conectando de um smartphone ou dispositivo móvel Windows Professional. Os dispositivos móveis permitem que os usuários estendam o alcance do Skype for Business. Este tópico descreve considerações de planejamento para o Skype for Business para Windows Phone que incluem a identificação de pré-requisitos e requisitos técnicos, componentes necessários e diretrizes de implantação.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Pré-requisitos do Skype for Business para Windows Phone

A seguir estão os pré-requisitos do Skype for Business para Windows Phone.
  
- Windows Phone 8.1 ou posterior.
    
- O dispositivo Windows Phone deve ter as atualizações mais recentes disponíveis na Microsoft. Para obter detalhes, consulte a seção do Windows Phone 8.1 no [histórico de atualizações do Windows Phone 8.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- O dispositivo deve ter 22 MB de espaço em disco disponível.
    
- O usuário precisa ter um plano de dados e voz para uma operadora.


## <a name="see-also"></a>Confira também

[Planejar-se para clientes de reuniões (aplicativo Web App e Reuniões)](meetings-clients.md)
  
[Requisitos de cliente do Skype for Business para Mac](mac-requirements.md)

[Baixar o Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos de sistema do Microsoft 365 e do Office](https://products.office.com/office-system-requirements)
