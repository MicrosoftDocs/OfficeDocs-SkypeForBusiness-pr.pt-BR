---
title: Eventos UCWA em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumo: saiba mais sobre a UCWA (Unified Communications Web API) no Skype for Business Server.'
ms.openlocfilehash: e4f36747ec75085785aefcd323f8fd6671bbbfe8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399635"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos UCWA em Skype for Business Server
 
**Resumo:** Saiba mais sobre a UCWA (Unified Communications Web API) no Skype for Business Server.
  
Skype for Business Server usa a UCWA (Unified Communications Web API) para várias finalidades, desde acessar o Microsoft Exchange para pesquisas de contato até a atualização da presença para clientes móveis.
  
O UCWA gravará registros de comportamento operacional como tipos de evento Informational, Warning e Error. A tabela a seguir descreve os eventos que podem ser escritos pelos componentes do UCWA.
  
|**ID do Evento**|**Tipo de evento**|**Resumo**|**Causa e resolução**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Erro  <br/> |O UCWA encontrou uma exceção inesperada durante a inicialização  <br/> |Ocorreu um erro inesperado durante a inicialização  <br/> Examine os detalhes de exceção na entrada de log de eventos associados para determinar a possível causa  <br/> |
|20003  <br/> |Erro  <br/> |O UCWA encontrou uma exceção não maneada  <br/> |Ocorreu uma exceção sem mão-de-mão  <br/> Reiniciar o servidor. Se o problema persistir, contate o suporte ao produto  <br/> |
|20004  <br/> |Erro  <br/> |Não é possível acessar Exchange para foto HD  <br/> |A conexão Exchange não está disponível  <br/> Certifique-se de que a conexão Exchange está disponível  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperado da falha ao acessar o Exchange para foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Erro  <br/> |Não é possível acessar Exchange para pesquisa de contatos  <br/> |A conexão Exchange não está disponível  <br/> Certifique-se de que a conexão Exchange está disponível  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperado da falha no contato de pesquisa no Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Aviso  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por aplicativo  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por aplicativo  <br/> Verifique se os clientes estão procurando assinaturas desnecessárias  <br/> |
|20009  <br/> |Aviso  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por lote  <br/> |Tentar inscrever mais do que as assinaturas de presença permitidas por lote  <br/> Verifique se os clientes estão procurando assinaturas desnecessárias  <br/> |
|20010  <br/> |Erro  <br/> |Não é possível recuperar dados de banda inband  <br/> |Não é possível recuperar dados de banda inband  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20011  <br/> |Erro  <br/> |Não é possível inscrever presença  <br/> |Não é possível inscrever presença  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20012  <br/> |Erro  <br/> |Falha ao registrar o ponto de extremidade  <br/> |Falha ao registrar o ponto de extremidade  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
|20013  <br/> |Erro  <br/> |A MCU de IM não está disponível  <br/> |A MCU de IM não está disponível  <br/> Veja se a MCU de IM está em execução  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao MCU de IM  <br/> |N/D  <br/> |
|20015  <br/> |Erro  <br/> |A AV MCU não está disponível  <br/> |A AV MCU não está disponível  <br/> Veja se o AV MCU está em execução  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao AV MCU  <br/> |N/D  <br/> |
|20017  <br/> |Erro  <br/> |AS MCU não está disponível  <br/> |AS MCU não está disponível  <br/> Veja se o AS MCU está em execução  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao AS MCU  <br/> |N/D  <br/> |
|20019  <br/> |Erro  <br/> |A MCU de dados não está disponível  <br/> |A MCU de dados não está disponível  <br/> Ver se o Data MCU está em execução  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperado de falha ao se conectar ao Data MCU  <br/> |N/D  <br/> |
|20021  <br/> |Erro  <br/> |Não é possível ingressar no MCU de IM  <br/> |Não é possível ingressar no MCU de IM  <br/> Veja se a MCU de IM está em execução  <br/> |
|20022  <br/> |Erro  <br/> |Não é possível ingressar no AV MCU  <br/> |Não é possível ingressar no AV MCU  <br/> Veja se o AV MCU está em execução  <br/> |
|20023  <br/> |Erro  <br/> |Não é possível ingressar como MCU  <br/> |Não é possível ingressar como MCU  <br/> Veja se o AS MCU está em execução  <br/> |
|20024  <br/> |Erro  <br/> |Não é possível ingressar no Data MCU  <br/> |Não é possível ingressar no Data MCU  <br/> Ver se o Data MCU está em execução  <br/> |
|20025  <br/> |Erro  <br/> |Não é possível acessar o Active Directory para fotos  <br/> |A conexão com o Active Directory não está disponível  <br/> Certifique-se de que a conexão com o Active Directory está disponível  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperado da falha ao acessar o Active Directory para fotos  <br/> |N/D  <br/> |
|20027  <br/> |Aviso  <br/> |Não é possível desterializar  <br/> |Não é possível desterializar  <br/> Se o problema persistir, contate o suporte ao produto  <br/> |
   

