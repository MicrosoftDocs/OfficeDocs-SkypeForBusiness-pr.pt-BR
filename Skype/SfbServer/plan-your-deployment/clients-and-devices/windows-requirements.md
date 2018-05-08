---
title: Suporte de software e os requisitos de cliente do Windows
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumo: Revise os requisitos de suporte do cliente Windows durante o planejamento Skype de negócios Server 2015.'
ms.openlocfilehash: 3dac3a8e15e53cec5605aa2b003150f491d8f2b5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Suporte de software e os requisitos de cliente do Windows
 
**Resumo:** Examine os requisitos de suporte do cliente Windows durante o planejamento Skype de negócios Server 2015.
  
Esta seção resume o software necessário para suportar o Skype para negócios 2015 2016 clientes e Windows.
  
Esses clientes são instalados quando instala o Office 365 e também estão disponíveis no [Download Skype para a empresa em todos os dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> O suplemento de Reunião Online para Skype para os negócios, que suporta o gerenciamento de reuniões de dentro do cliente de mensagens e colaboração do Outlook, instala automaticamente com Skype para negócios. 
  
**Software necessário para Skype para comerciais e o Reunião Online Add-in para Skype for Business**


|**Componente do sistema**|**Versões suportadas**|
|:-----|:-----|
|Sistema operacional Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operacional Windows 7  <br/> Windows Server 2008 R2 com service pack mais recente  <br/> **Observação:** Skype para a empresa e o suplemento de Reunião Online para Skype para negócios não são suportados no Windows Vista ou Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador de Internet do Internet Explorer 11  <br/>  Navegador de Internet do Internet Explorer 10 <br/> Navegador de Internet do Internet Explorer 9  <br/> Navegador de Internet do Internet Explorer 8  <br/> Navegador de Internet do Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/> **Observação:** Se você estiver usando o Skype for Business com o Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, o Internet Explorer 8 ou posterior é necessário.           |
|Integração com o Microsoft Office  <br/> |Para o conjunto completo de recursos de integração:  <br/> • Outlook 2016 cliente de mensagens e colaboração  <br/> • O outlook 2013 cliente de mensagens e colaboração  <br/> • O outlook 2010 cliente de mensagens e colaboração  <br/> |
|Integração com o Microsoft Exchange  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>Hardware

Consulte os [requisitos do sistema](https://products.office.com/en-us/office-system-requirements) do Office 365 para o hardware necessário para executar o Skype para o cliente de negócios.
  
## <a name="skype-for-business-web-app-browsers"></a>Skype para navegadores de aplicativo da Web de negócios

Skype para negócios Web App oferece suporte a combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [Planejar para clientes de reuniões (Web App e o aplicativo de reuniões)](meetings-clients.md). 
  
## <a name="microsoft-office-supportability"></a>Ajuste de Suporte do Microsoft Office

Skype para clientes corporativos Server 2015 suportam integração com diversas versões do Microsoft Office.
  
- Skype para recursos de integração de negócios são suportados no Outlook 2010, Outlook 2013 e Outlook 2016.
    
- Skype para recursos de integração de negócios são suportados no Microsoft Exchange Server 2016, Microsoft Exchange Server 2013 e Microsoft Exchange Server 2010.
    
- O suplemento de Reunião Online para Skype para a empresa é compatível com o Office 2016, Office 2013 e Microsoft Office 2010.
    
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você planeja usar o Skype para recursos de conferência de negócios, evite usando perfis obrigatórios do Active Directory Domain Services para entrar com o Skype para o cliente de negócios. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves de infraestrutura de chave pública (PKI) que são necessárias para Skype para conferências de negócios não podem ser salvos no perfil. 
  
## <a name="macintosh-operating-systems"></a>Sistemas operacionais Macintosh

O Skype para negócios nos requisitos de suporte do Mac são detalhadas na [Skype para negócios nos requisitos de cliente do Mac](mac-requirements.md).
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar para clientes de reuniões (Web App e reuniões App)](meetings-clients.md)
  
[Skype para negócios nos requisitos de cliente do Mac](mac-requirements.md)
#### 

[Baixe o Skype para a empresa em todos os dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos de sistema do Office 365](https://products.office.com/en-us/office-system-requirements)

