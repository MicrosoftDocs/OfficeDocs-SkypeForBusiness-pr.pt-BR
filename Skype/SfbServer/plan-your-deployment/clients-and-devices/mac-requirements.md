---
title: Skype for Business requisitos do cliente Mac
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar Skype for Business em um Mac.
ms.openlocfilehash: e25995173b44cf4f5892c1a34f77529042125c58
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014465"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business requisitos do cliente Mac
 
Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar Skype for Business em um Mac.
  
O [Skype for Business no Mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponível para download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware e software para Skype for Business no Mac

O Skype for Business no cliente Mac requer Mac OS X El Capitan e superior e usa pelo menos 100 MB de espaço em disco. Suportamos o uso de todos os dispositivos de áudio e vídeo integrados. Dispositivos externos devem ser listados [em Microsoft Teams dispositivos](https://www.microsoft.com/microsoft-teams/across-devices/devices). 
  
> [!NOTE]
> Esta lista é preliminar e alguns dispositivos podem ser qualificados para o Lync, mas não são compatíveis Skype for Business no Mac. Consulte os [requisitos do sistema](https://products.office.com/office-system-requirements) para o hardware mínimo necessário.
  
### <a name="legacy-mac-clients"></a>Clientes Mac herddos

Skype for Business Server 2015 também oferece suporte aos seguintes clientes herdados em computadores que estão executando o Mac OS 10.5.8 ou sistemas operacionais de versão ou service pack mais recentes (baseados em Intel) (o sistema operacional Mac OS 10.9 não tem suporte no momento). Para obter detalhes sobre recursos com suporte, consulte Comparação de recursos do cliente de área de [trabalho para Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync para Mac 2011 (consulte o Guia de Implantação do [Lync para Mac 2011](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator para Mac 2011 (consulte Communicator guia de implantação do [Mac 2011](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Esses clientes não são suportados pelo Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestrutura para Skype for Business no Mac
<a name="Infrastructure"> </a>

O Skype for Business no Cliente Mac aproveita a Plataforma de Gerenciamento de Comunicações Unificadas (UCMP) e a UCWA (Unified Communications Web API) que nossos clientes de mobilidade usam.
  
O cliente tem os mesmos requisitos que nossos clientes de mobilidade, pois você deve ter um Servidor de Borda de Acesso e Proxy Reverso implantados em uma configuração com suporte. 
  
### <a name="authentication"></a>Autenticação

O Skype for Business no cliente Mac oferece suporte à autenticação baseada em Certificado, Autenticação Moderna da Microsoft e Autenticação Multifafaionada quando implantado e habilitado.
  
> [!NOTE]
> Devido a uma limitação atual, as credenciais de Exchange do usuário devem ser as mesmas que suas Skype for Business credenciais. 
  
### <a name="certificates"></a>Certificados

Certificados em uso nos servidores de Borda de Acesso, Proxy Reverso e #A0 não devem usar o algoritmo de hash SHA-512.
  
A Lista de Revogação de Certificado HTTP deve ser definida e acessível pelo cliente. Por exemplo, não há suporte para uma entrada LDAP no certificado como sua Lista de Revogação de Certificados.
  
### <a name="dns"></a>DNS

A mobilidade deve ser implantada corretamente para que o Skype for Business no cliente Mac funcione corretamente. Um cenário de falha comum é ter as duas entradas DNS a seguir resolvêveis na rede interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Para obter mais informações, consulte: [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility), and the [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Confira também
<a name="Infrastructure"> </a>

[Requisitos dns para Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Perguntas Frequentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conhecidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)