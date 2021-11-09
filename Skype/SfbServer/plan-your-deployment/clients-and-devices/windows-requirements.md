---
title: Windows de cliente e suporte a software
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumo: revise os requisitos de suporte Windows cliente durante o planejamento Skype for Business Server.'
ms.openlocfilehash: b38c1d7a3565fbc2250766dbed3a0413b914388f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859898"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows de cliente e suporte a software
 
**Resumo:** Revise os requisitos Windows suporte ao cliente durante o planejamento Skype for Business Server.
  
Esta seção resume o software necessário para dar suporte aos Skype for Business Windows clientes. Esses clientes são instalados quando Microsoft 365 ou Office 365 instalados e também estão disponíveis em Baixar Skype for Business [em todos os seus dispositivos.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> O Complemento de Reunião Online para Skype for Business, que dá suporte ao gerenciamento de reuniões de dentro do cliente de Outlook de mensagens e colaboração, é instalado automaticamente com Skype for Business. 
  
**Software necessário para Skype for Business cliente e o Complemento de Reunião Online**

|**Componente do sistema**|**Versões com suporte**|
|:-----|:-----|
|Windows Sistema Operacional  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou posterior com service pack mais recente  <br/> **Observação:** Skype for Business e o Complemento de Reunião Online para Skype for Business não são suportados no Windows Vista ou Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador internet explorer 11  <br/>  Internet Explorer 10 Navegador da Internet <br/> Navegador da Internet do Internet Explorer 9  <br/> Navegador da Internet do Internet Explorer 8  <br/> Navegador da Internet do Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/>  Navegador da Web do Google Chrome  <br/>**Observação:** Se você estiver usando Skype for Business com Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, o Internet Explorer 8 ou posterior será necessário.           |
|Integração com o Microsoft Office  <br/> | Outlook 2010 ou posterior |
|Integração com o Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte os requisitos Microsoft 365 e Office [system](https://products.office.com/office-system-requirements) para o hardware necessário para executar o Skype for Business cliente.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype Aplicativo de Reuniões e Skype for Business Web App 

O Skype de reuniões e o Skype for Business Web App suportam combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você planeja usar os recursos de Skype for Business de conferência, evite usar perfis obrigatórios dos Serviços de Domínio do Active Directory para entrar no cliente Skype for Business cliente. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves PKI (infraestrutura de chave pública) necessárias para Skype for Business conferência não podem ser salvas no perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos do sistema para Skype for Business para Windows Phone
 
 
O Microsoft Skype for Business para Windows Phone fornece mensagens instantâneas (IM), presença aprimorada e telefonia para usuários em sua organização que estão se conectando a partir de um smartphone ou de um dispositivo móvel Windows Professional celular. Dispositivos móveis permitem que os usuários estendam o alcance de Skype for Business. Este tópico descreve considerações de planejamento para Skype for Business para Windows Phone que incluem a identificação de pré-requisitos e requisitos técnicos, componentes necessários e diretrizes de implantação.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business para Windows Phone Pré-requisitos

A seguir estão os Skype for Business para Windows Phone pré-requisitos.
  
- Windows Phone 8.1 ou posterior.
    
- O Windows Phone dispositivo deve ter as atualizações mais recentes disponíveis da Microsoft. Para obter detalhes, consulte a seção Windows Phone 8.1 em Windows Phone [8 histórico de atualizações.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- O dispositivo deve ter 22 MB de espaço em disco disponível.
    
- O usuário precisa ter um plano de dados e voz para uma operadora.


## <a name="see-also"></a>Confira também

[Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](meetings-clients.md)
  
[Skype for Business requisitos do cliente Mac](mac-requirements.md)

[Baixar Skype for Business todos os dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 e Office do sistema](https://products.office.com/office-system-requirements)
