---
title: Definir troncos adicionais no construtor de topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: saiba como definir um tronco adicional entre um servidor de mediação e um peer de gateway no construtor de topologias no Skype for Business Server.'
ms.openlocfilehash: afd8a37272d7450115f688bafe3627fb2689903c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767714"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir troncos adicionais no construtor de topologias no Skype for Business Server
 
**Resumo:** Saiba como definir um tronco adicional entre um servidor de mediação e um peer de gateway no construtor de topologias no Skype for Business Server.
  
Siga estas etapas para definir um tronco adicional ao qual você pode associar um par com um servidor de mediação. Um par fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN). Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP).
  
Um tronco é uma conexão lógica entre um servidor de mediação e um gateway.
  
> [!NOTE]
> Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação posicionado ou autônomo, conforme descrito em [definir um gateway no construtor de topologias no Skype for Business Server](define-a-gateway.md) na documentação de implantação.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um servidor de mediação e um gateway de mesmo nível

1. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.
    
2. Em Skype for Business Server, o nome do seu site, **componentes compartilhados**, clique com o botão direito do mouse no nó **troncos** e, em seguida, clique em **novo tronco**.
   1. Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Você não pode ter dois troncos com o mesmo nome.
    
      > [!NOTE]
      > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação. 
  
3. Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.
    5. Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, PBX de IP ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco. As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security). As portas da ramificação sobreviventes padrão são 5081 para TCP e 5082 para TLS.
    
4. Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.
    
    > [!NOTE]
    > Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS. 
  
5. Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse par
    
6. Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do par.
    
    > [!NOTE]
    > Com o suporte a vários troncos no Skype for Business Server, dois troncos com diferentes nomes de tronco não podem ser configurados com a mesma **porta do servidor de mediação associada** e **porta de escuta do gateway IP/PSTN**
  
    > [!NOTE]
    > Com o suporte a vários troncos no Skype for Business Server, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares. Ao definir um tronco, o número da **porta do servidor de mediação associado** deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido nos pools do Skype for Business Server e do servidor de mediação. Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione **Editar propriedades**. Specify the port range in the **Listening ports** field.
  
7. Clique em **OK**. 
    

