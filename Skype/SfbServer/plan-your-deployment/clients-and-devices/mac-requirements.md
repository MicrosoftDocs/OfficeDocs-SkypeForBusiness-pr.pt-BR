---
title: Skype para negócios nos requisitos de cliente do Mac
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leia este tópico para saber mais sobre o hardware, software e requisitos de infraestrutura para execução Skype para negócios em um Mac.
ms.openlocfilehash: 9fd03dbc04937dc34145c97a3abd4fc561ae0270
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503953"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype para negócios nos requisitos de cliente do Mac
 
Leia este tópico para saber mais sobre o hardware, software e requisitos de infraestrutura para execução Skype para negócios em um Mac.
  
O [Skype for Business no cliente Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) está disponível para download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de hardware e software do Skype for Business no Mac

O Skype for Business no cliente Mac requer Mac OS X El Capitan e superior e usa pelo menos 100MB de espaço em disco. Oferecemos suporte para o uso de dispositivos de áudio e vídeo totalmente integrados. Dispositivos externos devem estar na [lista de dispositivos qualificados para uso com o Lync](https://go.microsoft.com/fwlink/p/?LinkId=798223). 
  
> [!NOTE]
> Esta lista é preliminar e alguns dispositivos podem ser qualificados do Lync, mas não têm suporte em Skype for Business no Mac. > Consulte os [requisitos do sistema](https://products.office.com/en-us/office-system-requirements) para o hardware mínimo necessário.
  
### <a name="legacy-mac-clients"></a>Clientes herdados do Mac

Skype para Business Server 2015 também suporta os seguintes clientes herdados em computadores que estiverem executando o Mac OS 10.5.8 ou o service pack mais recente ou liberar (baseado em Intel) sistemas operacionais (sistema operacional de Mac SO 10,9 não é aceito atualmente). Para obter detalhes sobre recursos compatíveis, consulte [comparação de recursos do cliente de Desktop do Skype para negócios](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte [Lync para Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator para Mac 2011 (consulte [Communicator para Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268787))
    
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Requisitos de infraestrutura do Skype for Business no Mac
<a name="Infrastructure"> </a>

O Skype for Business no cliente Mac aproveita a plataforma de gerenciamento de comunicação unificada (UCMP), bem como o Unified Communications Web API (UCWA) que usam nossos clientes de mobilidade.
  
O cliente tem os mesmos requisitos que nossos clientes de mobilidade, de que você deve ter um Servidor de Borda de Acesso e um Proxy Reverso implantados em uma configuração compatível. Além disso, sua conta deve ser habilitada para Mobilidade.
  
### <a name="authentication"></a>Autenticação

O Skype for Business no cliente Mac oferece suporte a autenticação NTLM. Além disso, o cliente oferece suporte a autenticação moderna da Microsoft e Multi-Factor Authentication, quando implantadas e habilitadas.
  
> [!NOTE]
> Devido a uma limitação atual, as credenciais do usuário Exchange devem ser o mesmo que seus Skype credenciais de negócios. 
  
### <a name="certificates"></a>Certificados

Os certificados usados nos servidores de Borda de Acesso, Proxy Reverso e Front-End não podem usar o algoritmo de hash SHA-512.
  
A Lista de Revogação de Certificados HTTP deve ser definida e acessível pelo cliente. Por exemplo, não há suporte para uma entrada LDAP no certificado como sua lista de revogação de certificado.
  
### <a name="dns"></a>DNS

Mobilidade deve ser implantada corretamente para o Skype for Business no cliente Mac funcione corretamente. Uma situação de falha comum é ter as duas entradas DNS a seguir capazes de resolver na rede interna:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Para obter mais informações, consulte: [Implantação de mobilidade no Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e o [Guia de mobilidade do Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Ver também
<a name="Infrastructure"> </a>

[Requisitos de DNS para Skype para Business Server 2015](../../plan-your-deployment/network-requirements/dns.md)

[Perguntas frequentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conhecidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)