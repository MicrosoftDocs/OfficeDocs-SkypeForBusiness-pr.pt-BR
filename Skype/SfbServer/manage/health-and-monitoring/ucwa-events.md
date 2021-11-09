---
title: Eventos UCWA em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumo: saiba mais sobre a UCWA (Unified Communications Web API) no Skype for Business Server.'
ms.openlocfilehash: f4e1cfb344d8b27f2fef63f0c1c45ce1e4639627
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853015"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos UCWA em Skype for Business Server
 
**Resumo:** Saiba mais sobre a UCWA (Unified Communications Web API) no Skype for Business Server.
  
Skype for Business Server usa a UCWA (Unified Communications Web API) para várias finalidades, desde acessar o Microsoft Exchange para pesquisas de contato até a atualização da presença para clientes móveis.
  
O UCWA gravará registros de comportamento operacional como tipos de evento Informational, Warning e Error. A tabela a seguir descreve os eventos que podem ser escritos pelos componentes do UCWA.
  
|**ID do Evento**|**Tipo de evento**|**Resumo**|**Causa e resolução**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> Não disponível  <br/> |
|20002  <br/> |Error  <br/> |O UCWA encontrou uma exceção inesperada durante a inicialização  <br/> |Ocorreu um erro inesperado durante a inicialização  <br/> Examine os detalhes de exceção na entrada de log de eventos associados para determinar a possível causa  <br/> |
|20003  <br/> |Error  <br/> |O UCWA encontrou uma exceção não maneada  <br/> |Ocorreu uma exceção sem mão-de-mão  <br/> Reiniciar o servidor. Se o problema persistir, contate o suporte ao produto  <br/> |
|20004  <br/> |Error  <br/> |Não é possível acessar Exchange para foto HD  <br/> |A conexão Exchange não está disponível  <br/> Certifique-se de que a conexão Exchange está disponível  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperado da falha ao acessar o Exchange para foto HD  <br/> |Não disponível  <br/> |
|20006  <br/> |Error  <br/> |Não é possível acessar Exchange para pesquisa de contatos  <br/> |A conexão Exchange não está disponível  <br/> Certifique-se de que a conexão Exchange está disponível  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperado da falha no contato de pesquisa no Exchange  <br/> |Não disponível  <br/> |
|20008  <br/> |Aviso  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por aplicativo  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por aplicativo  <br/> Verifique se os clientes estão procurando assinaturas desnecessárias  <br/> |
|20009  <br/> |Aviso  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por lote  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por lote  <br/> Verifique se os clientes estão procurando assinaturas desnecessárias  <br/> |
|20010  <br/> |Error  <br/> |Não é possível recuperar dados de banda inband  <br/> |Não é possível recuperar dados de banda inband  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20011  <br/> |Error  <br/> |Não é possível inscrever presença  <br/> |Não é possível inscrever presença  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20012  <br/> |Error  <br/> |Falha ao registrar o ponto de extremidade  <br/> |Falha ao registrar o ponto de extremidade  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20013  <br/> |Error  <br/> |A MCU de IM não está disponível  <br/> |A MCU de IM não está disponível  <br/> Veja se a MCU de IM está em execução  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao MCU de IM  <br/> |Não disponível  <br/> |
|20015  <br/> |Error  <br/> |A AV MCU não está disponível  <br/> |A AV MCU não está disponível  <br/> Veja se o AV MCU está em execução  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao AV MCU  <br/> |Não disponível  <br/> |
|20017  <br/> |Error  <br/> |AS MCU não está disponível  <br/> |AS MCU não está disponível  <br/> Veja se o AS MCU está em execução  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao AS MCU  <br/> |Não disponível  <br/> |
|20019  <br/> |Error  <br/> |A MCU de dados não está disponível  <br/> |A MCU de dados não está disponível  <br/> Ver se o Data MCU está em execução  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao Data MCU  <br/> |Não disponível  <br/> |
|20021  <br/> |Error  <br/> |Não é possível ingressar no MCU de IM  <br/> |Não é possível ingressar no MCU de IM  <br/> Veja se a MCU de IM está em execução  <br/> |
|20022  <br/> |Error  <br/> |Não é possível ingressar no AV MCU  <br/> |Não é possível ingressar no AV MCU  <br/> Veja se o AV MCU está em execução  <br/> |
|20023  <br/> |Error  <br/> |Não é possível ingressar como MCU  <br/> |Não é possível ingressar como MCU  <br/> Veja se o AS MCU está em execução  <br/> |
|20024  <br/> |Error  <br/> |Não é possível ingressar no Data MCU  <br/> |Não é possível ingressar no Data MCU  <br/> Ver se o Data MCU está em execução  <br/> |
|20025  <br/> |Error  <br/> |Não é possível acessar o Active Directory para fotos  <br/> |A conexão com o Active Directory não está disponível  <br/> Certifique-se de que a conexão com o Active Directory está disponível  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperado da falha ao acessar o Active Directory para fotos  <br/> |Não disponível  <br/> |
|20027  <br/> |Aviso  <br/> |Não é possível desterializar  <br/> |Não é possível desterializar  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
   

