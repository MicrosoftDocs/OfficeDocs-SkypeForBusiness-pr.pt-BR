---
title: 'Lync Server 2013: executar testes de roteamento de voz informais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f916de228545a560c94bc45ea0a774ccc538c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Executar testes de roteamento de voz informais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-07_

Você pode usar a caixa de diálogo **criar informações do caso de teste de roteamento de voz** para executar testes informais antes de criar um caso de teste real. Quando você estiver satisfeito com o resultado de um teste, terá a opção de salvá-lo como um caso de teste formal.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>Para executar um teste de roteamento de voz informal

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de voz**e, em seguida, clique em **testar roteamento de voz**.

4.  Na página **testar roteamento de voz** , clique em **criar informações de caso de teste de roteamento de voz**.

5.  No campo **número discado** , digite o número de telefone que você deseja usar para este teste. Esse número será normalizado e exibido no campo **número normalizado** do painel de **resultados** .

6.  Na lista **plano de discagem** , selecione o plano de discagem a ser usado para testar o número discado. Padrão é o plano de discagem global.
    
    Quando você executar o teste, a primeira regra de normalização neste plano de discagem que corresponda ao número discado será exibida no campo **regra de normalização** do painel **resultados** .

7.  Na lista **política de voz** , selecione a política de voz a ser usada para testar o número discado. Padrão é a política de voz global.
    
    Quando você executar o teste, o primeiro registro de uso PSTN coincidente nesta política de voz será exibido no **primeiro campo uso PSTN** do painel de **resultados** . Além disso, a primeira rota de voz correspondente que está associada a este registro de uso PSTN será exibida no primeiro campo de **rota** .

8.  Adicionais Marque a caixa **de seleção popular do usuário** se desejar testar o número discado em relação à política de voz atribuída a um usuário específico.
    
    1.  Clique em **procurar** para exibir a caixa de diálogo **Selecionar usuários do Enterprise Voice** .
    
    2.  Clique em **Localizar** para exibir a lista de usuários que estão habilitados para o Enterprise Voice.
    
    3.  Clique duas vezes no nome do usuário cuja política de voz atribuída você deseja usar para esse teste. O campo **política** agora está preenchido com a política de voz atribuída ao usuário selecionado.
    
    Quando você executar o teste, o primeiro registro de uso de rede telefônica pública comutada (PSTN) nessa política de voz será exibido no **primeiro campo uso PSTN** do painel de **resultados** . Além disso, a primeira rota de voz correspondente que está associada a este registro de uso PSTN será exibida no primeiro campo de **rota** .

9.  Clique em **executar** para executar o caso de teste. Os resultados são mostrados no painel direito da caixa de diálogo.

10. Adicionais Clique em **salvar como** se você quiser salvar essa configuração de teste como um caso de teste formal.
    
    1.  No campo **nome** da caixa de diálogo **salvar informações do caso de teste de roteamento de voz** , digite um nome exclusivo para o caso de teste.
        
        O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz na sua implantação do Enterprise Voice. Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida (\\), ponto final (.) ou sublinhado (\_).
    
    2.  Observe que os campos restantes na caixa de diálogo **salvar informações do caso de teste de roteamento de voz** são somente leitura e são preenchidos com base na configuração *e* nos resultados informais do teste. Verifique se essa é a configuração que você deseja salvar para o caso de teste.
        
        <div>
        

        > [!NOTE]  
        > Os valores dos resultados do teste são usados para pré-popular campos na caixa de diálogo <STRONG>salvar informações do caso de teste de roteamento de voz</STRONG> da seguinte maneira: 
        > <UL>
        > <LI>
        > <P>A <STRONG>tradução esperada</STRONG> é preenchida previamente com o valor no campo <STRONG>número normalizado</STRONG> .</P>
        > <LI>
        > <P>A <STRONG>rota esperada</STRONG> é preenchida previamente com o valor no <STRONG>primeiro campo Route</STRONG> .</P>
        > <LI>
        > <P>O <STRONG>registro de uso de PSTN esperado</STRONG> é preenchido com o valor no primeiro campo de <STRONG>uso de PSTN</STRONG> .</P></LI></UL>Se as correspondências para qualquer um desses valores não forem encontradas durante a execução do teste, o campo correspondente estará vazio na caixa de diálogo <STRONG>salvar informações do caso de teste de roteamento de voz</STRONG> .

        
        </div>
    
    3.  Clique em **OK** para salvar o caso de teste ou clique em **Cancelar** para retornar para retornar à caixa de diálogo **Exibir informações do caso de teste de roteamento de voz** para desenvolver ainda mais o teste antes de salvá-lo.

11. Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar um caso de teste de roteamento de voz, você deve executar o comando <STRONG>Commit All</STRONG> para publicar o caso de teste. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um caso de teste de roteamento de voz no Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Executar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
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

