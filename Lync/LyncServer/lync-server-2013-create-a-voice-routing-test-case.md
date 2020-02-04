---
title: 'Lync Server 2013: Criar um caso de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Criar um caso de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Para criar um caso de teste

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de voz** e, em seguida, clique em **testar roteamento de voz**.

4.  Na página **testar roteamento de voz** , clique em **novo** para criar um novo caso de teste.

5.  Em **nome**, digite um nome exclusivo para o caso de teste.
    
    O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz na sua implantação do Enterprise Voice. Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida (\\), ponto final (.) ou sublinhado (\_).

6.  Em **número para testar**, digite o número discado que você deseja usar para testar a configuração de roteamento que você especificar para este caso de teste. Com base no plano de discagem, na rota e na política de voz, esse número será normalizado e exibido como saída.

7.  Na lista **plano de discagem** , selecione o plano de discagem a ser usado ao executar o teste. Padrão é o plano de discagem global.

8.  Na lista **política de voz** , selecione a política de voz a ser usada ao executar o teste. Padrão é a política de voz global.

9.  Na **tradução esperada**, digite o número de telefone no formato que você espera que ele seja exibido após a tradução. Esse é o valor do número de telefone que você está testando depois que ele foi traduzido pela primeira regra de normalização que corresponde ao plano de discagem selecionado. Quando você executar o caso de teste, se o número que você está testando não resultar no valor na **conversão esperada**, o teste falhará.

10. Adicionais Na lista de **uso de PSTN esperado** , você pode selecionar o registro de uso da rede de telefonia pública comutada (PSTN) que você espera usar quando executar o caso de teste, com base no plano de discagem e na política de voz especificados. Se um registro de uso PSTN diferente for usado, o teste falhará.

11. Adicionais Na lista de **rotas esperadas** , você pode selecionar a rota de voz que espera usar quando executar o caso de teste, com base no plano de discagem e na política de voz especificados. Se for usada uma rota de voz diferente, o teste falhará.

12. Adicionais Clique em **executar** para executar o caso de teste. Os resultados são mostrados no painel direito da página.

13. Clique em **OK**.

14. Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar um caso de teste de roteamento de voz, você deve executar o comando <STRONG>Commit All</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>
    
    Se o plano de discagem que está sendo empregado no teste normalizar números de telefone que comecem com um sinal de adição (por exemplo, + 12065551219), esse plano pode causar falha no teste de roteamento de voz. (O plano de discagem e a rota de voz funcionarão; na verdade, o teste-CsDialPlan será bem-sucedido. No entanto, o teste de roteamento de voz pode falhar.) Isso é algo a ter em mente ao testar rotas de voz.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exportar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

