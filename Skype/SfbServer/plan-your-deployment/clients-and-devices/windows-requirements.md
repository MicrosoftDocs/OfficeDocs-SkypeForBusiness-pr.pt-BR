---
title: Requisitos de cliente do Windows e suporte a software
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
description: 'Resumo: revise os requisitos de suporte do cliente do Windows durante o planejamento do Skype for Business Server.'
ms.openlocfilehash: 39f9efcd2008dacb653538b56f2aff3fcb8b7887
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928234"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisitos de cliente do Windows e suporte a software
 
**Resumo:** Examine os requisitos de suporte do cliente do Windows ao planejar o Skype for Business Server.
  
Esta seção resume o software necessário para dar suporte aos clientes do Windows do Skype for Business.  Esses clientes são instalados quando o Office 365 é instalado e também estão disponíveis no [download do Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> O suplemento de reunião online para o Skype for Business, que oferece suporte ao gerenciamento de reunião no cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o Skype for Business. 
  
**Software necessário para o cliente do Skype for Business e o suplemento de reunião online**

|**Componente do sistema**|**Versões suportadas**|
|:-----|:-----|
|Sistema operacional Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 ou posterior com o Service Pack mais recente  <br/> **Observação:** O Skype for Business e o suplemento de reunião online para o Skype for Business não têm suporte no Windows Vista ou Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador Internet Explorer 11  <br/>  Navegador Internet Explorer 10 <br/> Navegador Internet Explorer 9  <br/> Navegador Internet Explorer 8  <br/> Navegador Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/>  Navegador Google Chrome na Web  <br/>**Observação:** Se você estiver usando o Skype for Business com o Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, será necessário o Internet Explorer 8 ou posterior.           |
|Integração com o Microsoft Office  <br/> | Outlook 2010 ou posterior |
|Integração com o Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte os [requisitos do sistema](https://products.office.com/office-system-requirements) do Office 365 para o hardware necessário para executar o cliente Skype for Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Aplicativo de reuniões do Skype e Skype for Business Web App 

O aplicativo reuniões do Skype e o Skype for Business Web App dão suporte a combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [Plan for encontros clients (aplicativo Web e aplicativos de reuniões)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você planeja usar os recursos de conferência do Skype for Business, evite usar os perfis obrigatórios dos serviços de domínio Active Directory para entrar no cliente Skype for Business. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves PKI (infraestrutura de chave pública) necessárias para a conferência do Skype for Business não podem ser salvas no perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos do sistema para o Skype for Business para Windows Phone
 
 
O Microsoft Skype for Business para Windows Phone fornece mensagens instantâneas (IM), presença avançada e telefonia para usuários em sua organização que estão se conectando de um smartphone ou de um dispositivo móvel Windows Professional. Os dispositivos móveis permitem que os usuários ampliem o alcance do Skype for Business. Este tópico descreve as considerações de planejamento para o Skype for Business para Windows Phone que incluem a identificação de pré-requisitos e requisitos técnicos, componentes obrigatórios e orientações de implantação.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Pré-requisitos do Skype for Business para Windows Phone

A seguir estão os pré-requisitos do Skype for Business para Windows Phone.
  
- Windows Phone 8,1 ou posterior.
    
- O dispositivo Windows Phone deve ter as atualizações mais recentes disponíveis na Microsoft. Para obter detalhes, consulte a seção Windows Phone 8,1 no [histórico de atualização do Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- O dispositivo deve ter 22 MB de espaço em disco disponível.
    
- O usuário precisa ter um plano de dados e voz para uma operadora.


## <a name="see-also"></a>Confira também

[Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)](meetings-clients.md)
  
[Skype for Business nos requisitos do cliente Mac](mac-requirements.md)

[Baixar o Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos de sistema do Office 365](https://products.office.com/office-system-requirements)
