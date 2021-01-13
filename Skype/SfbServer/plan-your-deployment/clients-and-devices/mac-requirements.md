---
title: Requisitos de cliente do Skype for Business para Mac
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832161"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisitos de cliente do Skype for Business para Mac
 
Leia este tópico para saber mais sobre os requisitos de hardware, software e infraestrutura para executar o Skype for Business em um Mac.
  
O [Cliente Skype for Business para Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) está disponível para download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisitos de hardware e software para o Skype for Business no Mac

O cliente Skype for Business para Mac requer Mac OS X El Capitan e superior, e usa pelo menos 100 MB de espaço em disco. Suportamos o uso de todos os dispositivos de áudio e vídeo integrados. Dispositivos externos devem estar no [Catálogo de Soluções do Skype for Business.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Esta lista é preliminar e alguns dispositivos podem ser qualificados para o Lync, mas não são compatíveis com o Skype for Business no Mac. Consulte os [requisitos de sistema](https://products.office.com/office-system-requirements) para o hardware mínimo necessário.
  
### <a name="legacy-mac-clients"></a>Clientes Mac herddos

O Skype for Business Server 2015 também oferece suporte aos seguintes clientes herdados em computadores que executam o Mac OS 10.5.8 ou service pack ou os sistemas operacionais de versão mais recente (com base em Intel) (o sistema operacional Mac OS 10.9 não tem suporte no momento). Para obter detalhes sobre os recursos com suporte, consulte Comparação de recursos [do cliente da área de trabalho para o Skype for Business.](desktop-feature-comparison.md)
  
- Microsoft Lync para Mac 2011 (consulte o Guia de Implantação do [Lync para Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator para Mac 2011 (consulte o Guia de Implantação [do Communicator para Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
Esses clientes não são suportados pelo Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisitos de infraestrutura para o Skype for Business no Mac
<a name="Infrastructure"> </a>

O cliente Skype for Business para Mac utiliza a Plataforma de Gerenciamento de Comunicações Unificadas (UCMP), bem como a UCWA (Unified Communications Web API) que nossos clientes de mobilidade usam.
  
O cliente tem os mesmos requisitos que nossos clientes de mobilidade, pois você deve ter um Servidor de Borda de Acesso e Um Proxy Reverso implantados em uma configuração suportada. 
  
### <a name="authentication"></a>Autenticação

O cliente Skype for Business para Mac oferece suporte à autenticação baseada em certificados, autenticação moderna da Microsoft e autenticação multifa factor quando implantada e habilitada.
  
> [!NOTE]
> Devido a uma limitação atual, as credenciais do Exchange do usuário devem ser as mesmas que as credenciais do Skype for Business. 
  
### <a name="certificates"></a>Certificados

Os certificados em uso nos servidores de Borda de Acesso, Proxy Reverso e #A0 não devem usar o algoritmo de hash SHA-512.
  
A Lista de Revogação de Certificados HTTP deve ser definida e acessível pelo cliente. Por exemplo, não há suporte para uma entrada LDAP no certificado como sua Lista de Revogação de Certificados.
  
### <a name="dns"></a>DNS

A mobilidade deve ser implantada corretamente para que o Skype for Business no cliente Mac funcione corretamente. Um cenário de falha comum é ter as duas entradas DNS a seguir que podem ser resolvidos na rede interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Para obter mais informações, consulte: [Deploying Mobility in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224), and the [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Confira também
<a name="Infrastructure"> </a>

[Requisitos de DNS para o Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Perguntas Frequentes](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemas conhecidos](https://go.microsoft.com/fwlink/p/?LinkId=798228)
