# [Armazenamento de símbolo de diagnóstico](index.md)
## [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
### [Interface IBindingDisplay](ibindingdisplay-interface.md)
#### [Método GetCurrentDisplay](ibindingdisplay-getcurrentdisplay-method.md)
#### [Método InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)
### [Interface IDebugAutoAttach](idebugautoattach-interface.md)
#### [Método AutoAttach](idebugautoattach-autoattach-method.md)
### [Interface INotifyConnection2](inotifyconnection2-interface.md)
#### [Método RegisterNotifySource](inotifyconnection2-registernotifysource-method.md)
#### [Método UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
### [Interface INotifySink2](inotifysink2-interface.md)
#### [Método OnSyncCallEnter](inotifysink2-onsynccallenter-method.md)
#### [Método OnSyncCallExit](inotifysink2-onsynccallexit-method.md)
#### [Método OnSyncCallOut](inotifysink2-onsynccallout-method.md)
#### [Método OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md)
### [Interface INotifySource2](inotifysource2-interface.md)
#### [Método SetNotifyFilter](inotifysource2-setnotifyfilter-method.md)
### [Interface ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
#### [Método GetDocumentsForMethod](isymencunmanagedmethod-getdocumentsformethod-method.md)
#### [Método GetDocumentsForMethodCount](isymencunmanagedmethod-getdocumentsformethodcount-method.md)
#### [Método GetFileNameFromOffset](isymencunmanagedmethod-getfilenamefromoffset-method.md)
#### [Método GetLineFromOffset](isymencunmanagedmethod-getlinefromoffset-method.md)
#### [Método GetSourceExtentInDocument](isymencunmanagedmethod-getsourceextentindocument-method.md)
### [Interface ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)
#### [Método GetAsyncStepInfo](isymunmanagedasyncmethod-getasyncstepinfo-method.md)
#### [Método GetAsyncStepInfoCount](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)
#### [Método GetCatchHandlerILOffset](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)
#### [Método GetKickoffMethod](isymunmanagedasyncmethod-getkickoffmethod-method.md)
#### [Método HasCatchHandlerILOffset](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)
#### [Método IsAsyncMethod](isymunmanagedasyncmethod-isasyncmethod-method.md)
### [Interface ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md)
#### [Método DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)
#### [Método DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)
#### [Método DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)
### [Interface ISymUnmanagedBinder](isymunmanagedbinder-interface.md)
#### [Método GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)
#### [Método GetReaderFromStream](isymunmanagedbinder-getreaderfromstream-method.md)
### [Interface ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)
#### [Método GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md)
### [Interface ISymUnmanagedBinder3](isymunmanagedbinder3-interface.md)
#### [Método GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md)
### [Interface ISymUnmanagedConstant](isymunmanagedconstant-interface.md)
#### [Método GetName](isymunmanagedconstant-getname-method.md)
#### [Método GetSignature](isymunmanagedconstant-getsignature-method.md)
#### [Método GetValue](isymunmanagedconstant-getvalue-method.md)
### [Interface ISymUnmanagedDispose](isymunmanageddispose-interface.md)
#### [Método Destroy](isymunmanageddispose-destroy-method.md)
### [Interface ISymUnmanagedDocument](isymunmanageddocument-interface.md)
#### [Método FindClosestLine](isymunmanageddocument-findclosestline-method.md)
#### [Método GetCheckSum](isymunmanageddocument-getchecksum-method.md)
#### [Método GetCheckSumAlgorithmId](isymunmanageddocument-getchecksumalgorithmid-method.md)
#### [Método GetDocumentType](isymunmanageddocument-getdocumenttype-method.md)
#### [Método GetLanguage](isymunmanageddocument-getlanguage-method.md)
#### [Método GetLanguageVendor](isymunmanageddocument-getlanguagevendor-method.md)
#### [Método GetSourceLength](isymunmanageddocument-getsourcelength-method.md)
#### [Método GetSourceRange](isymunmanageddocument-getsourcerange-method.md)
#### [Método GetURL](isymunmanageddocument-geturl-method.md)
#### [Método HasEmbeddedSource](isymunmanageddocument-hasembeddedsource-method.md)
### [Interface ISymUnmanagedDocumentWriter](isymunmanageddocumentwriter-interface.md)
#### [Método SetCheckSum](isymunmanageddocumentwriter-setchecksum-method.md)
#### [Método SetSource](isymunmanageddocumentwriter-setsource-method.md)
### [Interface ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
#### [Método GetLocalVariableCount](isymunmanagedencupdate-getlocalvariablecount-method.md)
#### [Método GetLocalVariables](isymunmanagedencupdate-getlocalvariables-method.md)
#### [Método InitializeForEnc](isymunmanagedencupdate-initializeforenc-method.md)
#### [Método UpdateMethodLines](isymunmanagedencupdate-updatemethodlines-method.md)
#### [Método UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md)
### [Interface ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
#### [Método GetNamespace](isymunmanagedmethod-getnamespace-method.md)
#### [Método GetOffset](isymunmanagedmethod-getoffset-method.md)
#### [Método GetParameters](isymunmanagedmethod-getparameters-method.md)
#### [Método GetRanges](isymunmanagedmethod-getranges-method.md)
#### [Método GetRootScope](isymunmanagedmethod-getrootscope-method.md)
#### [Método GetScopeFromOffset](isymunmanagedmethod-getscopefromoffset-method.md)
#### [Método GetSequencePointCount](isymunmanagedmethod-getsequencepointcount-method.md)
#### [Método GetSequencePoints](isymunmanagedmethod-getsequencepoints-method.md)
#### [Método GetSourceStartEnd](isymunmanagedmethod-getsourcestartend-method.md)
#### [Método GetToken](isymunmanagedmethod-gettoken-method.md)
### [Interface ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)
#### [Método GetName](isymunmanagednamespace-getname-method.md)
#### [Método GetNamespaces](isymunmanagednamespace-getnamespaces-method.md)
#### [Método GetVariables](isymunmanagednamespace-getvariables-method.md)
### [Interface ISymUnmanagedReader](isymunmanagedreader-interface.md)
#### [Método GetDocument](isymunmanagedreader-getdocument-method.md)
#### [Método GetDocuments](isymunmanagedreader-getdocuments-method.md)
#### [Método GetDocumentVersion](isymunmanagedreader-getdocumentversion-method.md)
#### [Método GetGlobalVariables](isymunmanagedreader-getglobalvariables-method.md)
#### [Método GetMethod](isymunmanagedreader-getmethod-method.md)
#### [Método GetMethodByVersion](isymunmanagedreader-getmethodbyversion-method.md)
#### [Método GetMethodFromDocumentPosition](isymunmanagedreader-getmethodfromdocumentposition-method.md)
#### [Método GetMethodsFromDocumentPosition](isymunmanagedreader-getmethodsfromdocumentposition-method.md)
#### [Método GetMethodVersion](isymunmanagedreader-getmethodversion-method.md)
#### [Método GetNamespaces](isymunmanagedreader-getnamespaces-method.md)
#### [Método GetSymAttribute](isymunmanagedreader-getsymattribute-method.md)
#### [Método GetSymbolStoreFileName](isymunmanagedreader-getsymbolstorefilename-method.md)
#### [Método GetUserEntryPoint](isymunmanagedreader-getuserentrypoint-method.md)
#### [Método GetVariables](isymunmanagedreader-getvariables-method.md)
#### [Método Initialize](isymunmanagedreader-initialize-method.md)
#### [Método ReplaceSymbolStore](isymunmanagedreader-replacesymbolstore-method.md)
#### [Método UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)
### [Interface ISymUnmanagedReader2](isymunmanagedreader2-interface.md)
#### [Método GetMethodByVersionPreRemap](isymunmanagedreader2-getmethodbyversionpreremap-method.md)
#### [Método GetMethodsInDocument](isymunmanagedreader2-getmethodsindocument-method.md)
#### [Método GetSymAttributePreRemap](isymunmanagedreader2-getsymattributepreremap-method.md)
### [Interface ISymUnmanagedReaderSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-interface.md)
#### [Método GetSymbolSearchInfoCount](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)
#### [Método GetSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)
### [Interface ISymUnmanagedScope](isymunmanagedscope-interface.md)
#### [Método GetChildren](isymunmanagedscope-getchildren-method.md)
#### [Método GetEndOffset](isymunmanagedscope-getendoffset-method.md)
#### [Método GetLocalCount](isymunmanagedscope-getlocalcount-method.md)
#### [Método GetLocals](isymunmanagedscope-getlocals-method.md)
#### [Método GetMethod](isymunmanagedscope-getmethod-method.md)
#### [Método GetNamespaces](isymunmanagedscope-getnamespaces-method.md)
#### [Método GetParent](isymunmanagedscope-getparent-method.md)
#### [Método GetStartOffset](isymunmanagedscope-getstartoffset-method.md)
### [Interface ISymUnmanagedScope2](isymunmanagedscope2-interface.md)
#### [Método GetConstantCount](isymunmanagedscope2-getconstantcount-method.md)
#### [Método GetConstants](isymunmanagedscope2-getconstants-method.md)
### [Interface ISymUnmanagedSourceServerModule](isymunmanagedsourceservermodule-interface.md)
#### [Método GetSourceServerData](isymunmanagedsourceservermodule-getsourceserverdata-method.md)
### [Interface ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md)
#### [Método GetHRESULT](isymunmanagedsymbolsearchinfo-gethresult-method.md)
#### [Método GetSearchPath](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)
#### [Método GetSearchPathLength](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)
### [Interface ISymUnmanagedVariable](isymunmanagedvariable-interface.md)
#### [Método GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)
#### [Método GetAddressField2](isymunmanagedvariable-getaddressfield2-method.md)
#### [Método GetAddressField3](isymunmanagedvariable-getaddressfield3-method.md)
#### [Método GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)
#### [Método GetAttributes](isymunmanagedvariable-getattributes-method.md)
#### [Método GetEndOffset](isymunmanagedvariable-getendoffset-method.md)
#### [Método GetName](isymunmanagedvariable-getname-method.md)
#### [Método GetSignature](isymunmanagedvariable-getsignature-method.md)
#### [Método GetStartOffset](isymunmanagedvariable-getstartoffset-method.md)
### [Interface ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
#### [Método Abort](isymunmanagedwriter-abort-method.md)
#### [Método Close](isymunmanagedwriter-close-method.md)
#### [Método CloseMethod](isymunmanagedwriter-closemethod-method.md)
#### [Método CloseNamespace](isymunmanagedwriter-closenamespace-method.md)
#### [Método CloseScope](isymunmanagedwriter-closescope-method.md)
#### [Método DefineConstant](isymunmanagedwriter-defineconstant-method.md)
#### [Método DefineDocument](isymunmanagedwriter-definedocument-method.md)
#### [Método DefineField](isymunmanagedwriter-definefield-method.md)
#### [Método DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)
#### [Método DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
#### [Método DefineParameter](isymunmanagedwriter-defineparameter-method.md)
#### [Método DefineSequencePoints](isymunmanagedwriter-definesequencepoints-method.md)
#### [Método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md)
#### [Método Initialize](isymunmanagedwriter-initialize-method.md)
#### [Método Initialize2](isymunmanagedwriter-initialize2-method.md)
#### [Método OpenMethod](isymunmanagedwriter-openmethod-method.md)
#### [Método OpenNamespace](isymunmanagedwriter-opennamespace-method.md)
#### [Método OpenScope](isymunmanagedwriter-openscope-method.md)
#### [Método RemapToken](isymunmanagedwriter-remaptoken-method.md)
#### [Método SetMethodSourceRange](isymunmanagedwriter-setmethodsourcerange-method.md)
#### [Método SetScopeRange](isymunmanagedwriter-setscoperange-method.md)
#### [Método SetSymAttribute](isymunmanagedwriter-setsymattribute-method.md)
#### [Método SetUserEntryPoint](isymunmanagedwriter-setuserentrypoint-method.md)
#### [Método UsingNamespace](isymunmanagedwriter-usingnamespace-method.md)
### [Interface ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
#### [Método DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)
#### [Método DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)
#### [Método DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)
### [Interface ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
#### [Método Commit](isymunmanagedwriter3-commit-method.md)
#### [Método OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)
### [Interface ISymUnmanagedWriter4](isymunmanagedwriter4-interface.md)
#### [Método GetDebugInfoWithPadding](isymunmanagedwriter4-getdebuginfowithpadding-method.md)
### [Interface ISymUnmanagedWriter5](isymunmanagedwriter5-interface.md)
#### [Método CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)
#### [Método MapTokenToSourceSpan](isymunmanagedwriter5-maptokentosourcespan-method.md)
#### [Método OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)
## [Enumerações de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-enumerations.md)
### [Enumeração CorSymAddrKind](corsymaddrkind-enumeration.md)
### [Enumeração CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md)
### [Enumeração CorSymVarFlag](corsymvarflag-enumeration.md)
### [Enumeração NOTIFY_FILTER](notify-filter-enumeration.md)
## [Estruturas de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-structures.md)
### [Estrutura CALL_ID](call-id-structure.md)
### [Estrutura SYMLINEDELTA](symlinedelta-structure.md)
### [Estrutura USER_THREAD](user-thread-structure.md)
