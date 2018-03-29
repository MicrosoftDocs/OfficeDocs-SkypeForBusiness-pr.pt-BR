---
title: Definir troncos adicionais no Construtor de Topologias no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: Saiba como definir um tronco adicional entre um servidor de mediação e um par de gateway no construtor de topologia no Skype para Business Server 2015.'
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a>Definir troncos adicionais no Construtor de Topologias no Skype for Business Server 2015
 
**Resumo:** Saiba como definir um tronco adicional entre um servidor de mediação e um par de gateway no construtor de topologia no Skype para Business Server 2015.
  
Siga estas etapas para definir um tronco adicional para o qual você pode associar um ponto com um servidor de mediação. Um ponto fornece aos usuários habilitados para o Enterprise Voice com conectividade para a comutação telefônica PSTN (rede pública). Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP).
  
Um tronco é uma conexão lógica entre um servidor de mediação e um gateway.
  
> [!NOTE]
> Este tópico pressupõe que você tenha o programa de instalação um gateway PSTN e tronco raiz com pelo menos um servidor de mediação autônomo ou posicionado pool ou, conforme descrito em [definir um gateway no construtor de topologia no Skype para Business Server 2015](define-a-gateway.md) na documentação de implantação.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um servidor de mediação e um par de gateway

1. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.
    
2. Em Skype para Business Server, o nome do seu site, **Componentes compartilhados**, clique com botão direito no nó **troncos** e clique em **Novo tronco**.
    3. Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Você não pode ter dois troncos com o mesmo nome.
    
    > [!NOTE]
    > Se você especificar a segurança de camada de transporte (TLS) como o tipo de transporte, você deve especificar o FQDN ao invés do endereço IP do ponto do servidor de mediação. 
  
4. Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.
    5. Em **Porta de escuta do gateway PSTN**, digite a porta de escuta do ponto (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do servidor de mediação que deve ser associado esse tronco. As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security). As portas de aparelho de filial persistente padrão são 5081 para TCP e 5082 para TLS.
    
6. Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.
    
    > [!NOTE]
    > Por motivos de segurança, é altamente recomendável que você implante um par ao servidor de mediação que possa utilizar TLS. 
  
7. Em **Servidor de mediação associado**, selecione o pool de servidor de mediação para associar o tronco raiz deste ponto
    
8. Em **porta do servidor de mediação associado**, digite a porta de escuta do servidor de mediação receberá mensagens SIP do ponto.
    
    > [!NOTE]
    > Com suporte a troncos múltiplos no Skype para Business Server, dois troncos com nomes de tronco diferentes podem ser configurados com a mesma **porta do servidor de mediação associado** e **Porta de escuta do gateway IP/PSTN**
  
    > [!NOTE]
    > Com suporte a troncos múltiplos no Skype para Business Server, as portas de sinalização do SIP de vários pode ser definido no servidor de mediação para comunicação com vários correspondentes. Ao definir um tronco, o número da **porta do servidor de mediação associado** deve ser dentro do intervalo das portas de escuta para o protocolo respectivo permitidos pelo servidor de mediação. Esse intervalo de portas é definido em Skype para pools Business Server e o servidor de mediação. O pool do servidor de mediação relevante do mouse em e selecione **Editar propriedades**. Especifique o intervalo de portas no campo **Portas de escuta**.
  
9. Clique em **OK**. 
    

