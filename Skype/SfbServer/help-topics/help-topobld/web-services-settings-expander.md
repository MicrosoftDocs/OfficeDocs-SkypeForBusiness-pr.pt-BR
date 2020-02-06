---
title: Expansor de Configurações de Serviços Web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: No construtor de topologias, você pode modificar as configurações de porta usadas para os serviços Web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga de DNS (sistema de nomes de domínio), poderá usar o construtor de topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que é resolvido para os endereços IP físicos de todos os servidores desse pool.
ms.openlocfilehash: ab2a93bab1717bc34e0df42fb7f4a9ed5298166c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819023"
---
# <a name="web-services-settings-expander"></a>Expansor de Configurações de Serviços Web
 
No construtor de topologias, você pode modificar as configurações de porta usadas para os serviços Web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga de DNS (sistema de nomes de domínio), poderá usar o construtor de topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que é resolvido para os endereços IP físicos de todos os servidores desse pool.
  
### <a name="editing-web-services-settings"></a>Editando Configurações de Serviços Web

1. Selecione o servidor Front-Ends Standard Edition ou o pool de Front-Ends Enterprise Edition apropriado, e clique em **Editar Propriedades**.
    
2. Na caixa de diálogo **Editar Propriedades**, clique na guia **Serviços Web**.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN dos serviços Web externos deve ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como **pool01.contoso.com**, não será possível usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.
  
3. Caso esteja editando as propriedades de um pool Enterprise Edition, você terá a opção de escolher **Substituir FQDN**. Essa opção só deverá ser selecionada se você estiver usando balanceamento de carga DNS. Se estiver usando o balanceamento de carga DNS, selecione **Substituir FQDN** e, na caixa de texto, digite o FQDN do pool que resolve para todos os endereços IP físicos dos servidores no pool em questão. Se não estiver usando o balanceamento de carga DNS e não selecionar **Substituir FQDN**, você não poderá alterar o FQDN dos serviços Web internos. O FQDN de serviços Web internos é a URL usada por usuários internos para se conectar ao Skype for Business Server.
    
4. Insira, opcionalmente, novos valores HTTP, HTTPS ou HTTP e HTTPS para as **Portas de escuta** e as **Portas publicadas**. Portas de escuta são as portas usadas pelos Serviços de Informações da Internet (IIS) para escutar por tráfego SIP (Session Initiation Protocol) de entrada; portas publicadas são portas configuradas em um balanceador de carga ou servidor de proxy reverso e também são usadas para escutar o tráfego SIP de entrada. Por padrão, tanto a porta de escuta HTTP quanto a porta publicada HTTP estão definidas à porta 80; as portas HTTPS correspondentes estão ambas definidas à 443. O valor padrão para as duas portas publicadas HTTP é 8080 e as portas HTTPS correspondentes estão definidas como 4443.
    
5. Clique em **OK**.
    
Caso modifique o FQDN interno ou qualquer uma das atribuições de porta de escuta, você deve executar novamente uma configuração local em todos os servidores no pool para que essas alterações tenham efeito.
  

