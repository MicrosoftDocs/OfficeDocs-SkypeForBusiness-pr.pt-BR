---
title: Suporte de software e os requisitos de cliente do Windows
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Resumo: Revise os requisitos de suporte do cliente Windows ao planejar a Skype Business Server.'
ms.openlocfilehash: 5eda349b18930506e1ff6167804a11ca29c7190a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890977"
---
# <a name="windows-client-requirements-and-software-support"></a>Suporte de software e os requisitos de cliente do Windows
 
**Resumo:** Examine os requisitos de suporte do cliente Windows ao planejar a Skype Business Server.
  
Esta seção resume o software necessário para suportar o Skype para clientes Windows de negócios.  Esses clientes são instalados quando instala o Office 365 e também estão disponíveis no [Download Skype para a empresa em todos os dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> O suplemento de Reunião Online para Skype para os negócios, que suporta o gerenciamento de reuniões de dentro do cliente de mensagens e colaboração do Outlook, instala automaticamente com Skype para negócios. 
  
**Software necessário para Skype para o cliente de negócios e o suplemento de Reunião Online**

|**Componente do sistema**|**Versões suportadas**|
|:-----|:-----|
|Sistema operacional Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Sistema operacional Windows 7  <br/> Windows Server 2008 R2 ou posterior com o service pack mais recente  <br/> **Observação:** Skype para a empresa e o suplemento de Reunião Online para Skype para negócios não são suportados no Windows Vista ou Windows XP (qualquer versão). <br/> |
|Instalação e atualizações  <br/> |Direitos e permissões de administrador  <br/> |
|Navegador  <br/> |Microsoft Edge  <br/> Navegador de Internet do Internet Explorer 11  <br/>  Navegador de Internet do Internet Explorer 10 <br/> Navegador de Internet do Internet Explorer 9  <br/> Navegador de Internet do Internet Explorer 8  <br/> Navegador de Internet do Internet Explorer 7  <br/> Navegador da Web Mozilla Firefox  <br/>  Navegador da web Google Chrome  <br/>**Observação:** Se você estiver usando o Skype for Business com o Microsoft Exchange Online e sua organização tiver implantado um proxy HTTP de autenticação, o Internet Explorer 8 ou posterior é necessário.           |
|Integração com o Microsoft Office  <br/> | Outlook 2010 ou posterior |
|Integração com o Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 ou posterior  | 
   
## <a name="hardware"></a>Hardware

Consulte os [requisitos do sistema](https://products.office.com/en-us/office-system-requirements) do Office 365 para o hardware necessário para executar o Skype para o cliente de negócios.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype reuniões App e Skype para negócios Web App 

O Skype reuniões App e o Skype para negócios Web App oferecem suporte a combinações específicas de sistemas operacionais e navegadores. Para obter detalhes, consulte [Planejar para clientes de reuniões (Web App e o aplicativo de reuniões)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Usando perfis obrigatórios

Se você planeja usar o Skype para recursos de conferência de negócios, evite usando perfis obrigatórios do Active Directory Domain Services para entrar com o Skype para o cliente de negócios. Como os perfis obrigatórios são perfis de usuário somente leitura, as chaves de infraestrutura de chave pública (PKI) que são necessárias para Skype para conferências de negócios não podem ser salvos no perfil. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisitos do sistema do Skype for Business para Windows Phone
 
 
Microsoft Skype para Business para Windows Phone fornece mensagens instantâneas (IM), presença avançada e telefonia para usuários em sua organização que estiverem se conectando de um smartphone ou um dispositivo móvel do Windows Professional. Dispositivos móveis permitem que os usuários ampliem o alcance do Skype para negócios. Este tópico descreve as considerações de planejamento para Skype para Business para Windows Phone que incluem a identificação de pré-requisitos e requisitos técnicos, componentes necessários e orientações sobre a implantação.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Pré-requisitos do Skype for Business para Windows Phone

A seguir estão o Skype para pré-requisitos de negócios para o Windows Phone.
  
- Windows Phone 8.1 ou posterior.
    
- O dispositivo com Windows Phone precisa ter as atualizações mais recentes disponíveis na Microsoft. Para obter detalhes, consulte a seção de Windows Phone 8.1 no [histórico de atualização do Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- O dispositivo precisa ter 22 MB de espaço em disco disponível.
    
- O usuário precisa ter um plano de dados e voz para uma operadora.


## <a name="see-also"></a>Consulte também

[Planejar para clientes de reuniões (Web App e reuniões App)](meetings-clients.md)
  
[Skype para negócios nos requisitos de cliente do Mac](mac-requirements.md)

[Baixe o Skype para a empresa em todos os dispositivos](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisitos de sistema do Office 365](https://products.office.com/en-us/office-system-requirements)