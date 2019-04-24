---
title: Expansor de Configurações de Serviços Web
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Construtor de topologia, você pode modificar as configurações de porta usadas para ambos os seus serviços web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga de sistema de nome de domínio (DNS), você pode usar o construtor de topologias para configurar o nome de domínio totalmente qualificado (FQDN) do pool que resolve para os endereços IP físicos de todos os servidores desse pool.
ms.openlocfilehash: 75d73a81ec649c97149fd03125887116c947144c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201456"
---
# <a name="web-services-settings-expander"></a>Expansor de Configurações de Serviços Web
 
Construtor de topologia, você pode modificar as configurações de porta usadas para ambos os seus serviços web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga de sistema de nome de domínio (DNS), você pode usar o construtor de topologias para configurar o nome de domínio totalmente qualificado (FQDN) do pool que resolve para os endereços IP físicos de todos os servidores desse pool.
  
### <a name="editing-web-services-settings"></a>Editando Configurações de Serviços Web

1. Selecione o servidor Front-Ends Standard Edition ou o pool de Front-Ends Enterprise Edition apropriado, e clique em **Editar Propriedades**.
    
2. Na caixa de diálogo **Editar Propriedades**, clique na guia **Serviços Web**.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de Front-End ou servidor Front-End, os serviços Web externos FQDN deve ser exclusivo. Por exemplo, se você definir os serviços Web externos FQDN de um servidor Front-End como **pool01. contoso.com**, você não pode usar **pool01. contoso.com** para outro pool de Front-End ou servidor Front-End. Se você estiver implantando o diretores também, o external FQDN definido para qualquer Diretor de serviços da Web ou pool de diretores deve ser exclusivo de qualquer outro diretor ou diretor do pool, bem como qualquer pool Front-End ou servidor Front-End. Se você decidir substituir os serviços web internos com um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, diretor ou um pool de diretores.
  
3. Caso esteja editando as propriedades de um pool Enterprise Edition, você terá a opção de escolher **Substituir FQDN**. Essa opção só deverá ser selecionada se você estiver usando balanceamento de carga DNS. Se estiver usando o balanceamento de carga DNS, selecione **Substituir FQDN** e, na caixa de texto, digite o FQDN do pool que resolve para todos os endereços IP físicos dos servidores no pool em questão. Se não estiver usando o balanceamento de carga DNS e não selecionar **Substituir FQDN**, você não poderá alterar o FQDN dos serviços Web internos. Os serviços web internos FQDN é a URL usada pelos usuários internos para conectar Skype para Business Server.
    
4. Insira, opcionalmente, novos valores HTTP, HTTPS ou HTTP e HTTPS para as **Portas de escuta** e as **Portas publicadas**. Portas de escuta são as portas usadas pelos Serviços de Informações da Internet (IIS) para escutar por tráfego SIP (Session Initiation Protocol) de entrada; portas publicadas são portas configuradas em um balanceador de carga ou servidor de proxy reverso e também são usadas para escutar o tráfego SIP de entrada. Por padrão, tanto a porta de escuta HTTP quanto a porta publicada HTTP estão definidas à porta 80; as portas HTTPS correspondentes estão ambas definidas à 443. O valor padrão para as duas portas publicadas HTTP é 8080 e as portas HTTPS correspondentes estão definidas como 4443.
    
5. Clique em **OK**.
    
Caso modifique o FQDN interno ou qualquer uma das atribuições de porta de escuta, você deve executar novamente uma configuração local em todos os servidores no pool para que essas alterações tenham efeito.
  

