---
title: Definir troncos adicionais no Construtor de Topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba como definir um tronco adicional entre um Servidor de Mediação e um par de gateway no Construtor de Topologias no Skype for Business Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836991"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir troncos adicionais no Construtor de Topologias no Skype for Business Server
 
**Resumo:** Saiba como definir um tronco adicional entre um Servidor de Mediação e um par de gateway no Construtor de Topologias no Skype for Business Server.
  
Siga estas etapas para definir um tronco adicional ao qual você pode associar um par a um Servidor de Mediação. Um par fornece aos usuários habilitados para o Enterprise Voice a conectividade com a Rede Telefônica Pública Comuada (PSTN). Um par pode ser um gateway PSTN, um IP-PBX ou um Controlador de Borda de Sessão (SBC) para um ITSP (Provedor de Serviços de Telefonia da Internet).
  
Um tronco é uma conexão lógica entre um Servidor de Mediação e um gateway.
  
> [!NOTE]
> Este tópico presume que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um Servidor de Mediação ou pool autônomo ou colocal, conforme descrito em [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) na documentação de Implantação.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um Servidor de Mediação e um par de gateway

1. Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.
    
2. Em Skype for Business Server, seu nome de **site,** **Componentes Compartilhados** , clique com o botão direito do mouse no nó Troncos e clique em **Novo Tronco.**
   1. Em **Definir Novo Tronco,** especifique um nome amigável para identificar exclusivamente o tronco. Não é possível ter dois troncos com o mesmo nome.
    
      > [!NOTE]
      > Se você especificar o protocolo TLS como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do ponto do Servidor de Mediação. 
  
3. Em **Gateway PSTN Associado,** selecione o par de gateway PSTN a ser associado a esse tronco.
    5. Em Porta de Escuta para **gateway PSTN,** digite a porta de escuta que o par (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do Servidor de Mediação que será associado a esse tronco. As portas pares padrão são 5066 para Protocolo de Controle de Transmissão (TCP) e 5067 para TLS (Transport Layer Security). As portas padrão do Aparelho de Filial São 5081 para TCP e 5082 para TLS.
    
4. Em **Protocolo de Transporte SIP,** clique no tipo de transporte que o par usa.
    
    > [!NOTE]
    > Por motivos de segurança, recomendamos que você implante um par para o Servidor de Mediação que possa usar TLS. 
  
5. Em **Servidor de Mediação Associado,** selecione o pool do Servidor de Mediação a ser associado ao tronco raiz deste par
    
6. Em **Porta do Servidor de Mediação** Associado, digite a porta de escuta que o Servidor de Mediação receberá mensagens SIP do par.
    
    > [!NOTE]
    > Com suporte a vários troncos no Skype for Business Server, dois  troncos com nomes de tronco diferentes não podem ser configurados com a mesma porta do Servidor de Mediação Associada e Porta de Escuta para **gateway IP/PSTN**
  
    > [!NOTE]
    > Com suporte a vários troncos no Skype for Business Server, várias portas de sinalização SIP podem ser definidas no Servidor de Mediação para comunicação com vários pares. Ao definir um tronco, o número da porta do Servidor de Mediação Associado deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo Servidor de Mediação.  Esse intervalo de portas é definido em pools do Skype for Business Server e do Servidor de Mediação. Clique com o botão direito do mouse no pool do Servidor de Mediação relevante e selecione **Editar Propriedades.** Especifique a faixa de porta no campo **Portas de ouvinte**.
  
7. Clique em **OK**. 
    

