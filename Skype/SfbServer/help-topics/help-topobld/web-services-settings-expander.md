---
title: Expansor de Configurações de Serviços da Web
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: No Construtor de Topologias, você pode modificar as configurações de porta usadas para seus serviços Web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga DNS (Sistema de Nomes de Domínio), poderá usar o Construtor de Topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que se resolve para os endereços IP físicos de todos os servidores nesse pool.
ms.openlocfilehash: 66dc22bed1d8e5e24f5403fec9cfa8c2924c810d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854395"
---
# <a name="web-services-settings-expander"></a>Expansor de Configurações de Serviços da Web
 
No Construtor de Topologias, você pode modificar as configurações de porta usadas para seus serviços Web internos e externos. Além disso, e se você estiver implantando o balanceamento de carga DNS (Sistema de Nomes de Domínio), poderá usar o Construtor de Topologias para configurar o FQDN (nome de domínio totalmente qualificado) do pool que se resolve para os endereços IP físicos de todos os servidores nesse pool.
  
### <a name="editing-web-services-settings"></a>Editando Definições de Serviços Web

1. Selecione o servidor Front-Ends Standard Edition ou o pool de Front-Ends Enterprise Edition apropriado e então clique em **Editar Propriedades**.
    
2. Na caixa de diálogo **Editar Propriedades**, clique na guia **Serviços Web**.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de Front-End ou Servidor Front-End, o FQDN de serviços Web externos deve ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor Front-End como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de Front-End ou Servidor Front-End. Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deve ser exclusivo de qualquer outro diretor ou pool de diretores, bem como qualquer pool de Front-End ou Servidor Front-End. Se você decidir substituir os serviços Web internos por um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, Diretor ou pool de Diretores.
  
3. Caso esteja editando as propriedades de um pool Enterprise Edition, você terá a opção de escolher **Substituir FQDN**. Esta opção deve ser selecionada apenas caso esteja usando balanceamento de carga DNS (Domain Name System). Se estiver usando balanceamento de carga DNS, selecione **Substituir FQDN** e, na caixa de texto, digite o FQDN do pool que resolve para todos os endereços IP físicos dos servidores no pool em questão. Caso não esteja usando balanceamento de carga DNS e não selecionar **Substituir FQDN**, você não poderá alterar o FQDN dos serviços web internos. O FQDN de serviços Web internos é a URL usada por usuários internos para se conectar a Skype for Business Server.
    
4. Insira, opcionalmente, novos valores HTTP, HTTPS ou HTTP e HTTPS para as **Portas de escuta** e as **Portas publicadas**. Portas de escuta são as portas usadas pelos IIS (Internet Information Services) para escutar por tráfego SIP (Session Initiation Protocol) de entrada; portas publicadas são portas configuradas em um balanceador de carga ou servidor de proxy reverso e também são usadas para escutar o tráfego SIP de entrada. Por padrão, tanto a porta de escuta HTTP quanto a porta publicada HTTP estão definidas à porta 80; as portas HTTPS correspondentes estão ambas definidas à 443. O valor padrão para as duas portas publicadas HTTP é 8080 e as portas HTTPS correspondentes estão definidas como 4443.
    
5. Clique em **OK**.
    
Caso você modifique o FQDN interno ou qualquer uma das atribuições de porta de escuta, você deve executar novamente uma configuração local em todos os servidores no pool para que essas mudanças tenham efeito.
  

