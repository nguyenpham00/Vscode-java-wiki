Set the following property: 
```
"java.settings.url": "/home/<your_name>/settings.prefs",
```

The property can point to an URL or a local file path.

You can also define the settings preferences in your project's [`.settings/org.eclipse.jdt.core.prefs`](https://gist.github.com/snjeza/e59f0ce031f237a9d0f4f2aec404a4bb). It will override global settings.

The best way to create those preferences is to edit it in Eclipse.

In Eclipse, right-click on your project, open `Window` >`Preferences` > `Java Code Style` > `Formatter`,  `Window` >`Preferences` > `Java` > `Code Style` > `Organize Imports`, `Window` >`Preferences` > `Java` > `Compiler` > `Errors/Warnings` and create a new settings file :

![Eclipse Preferences](https://github.com/snjeza/vscode-test/raw/master/.github/images/settings.png)

The preferences file can be exported using `File` > `Export` > `General` > `Preferences`. You can use this file to define `java.settings.url`.

## Java Compiler Options

`org.eclipse.jdt.core.compiler.codegen.inlineJsrBytecode` *Inline JSR Bytecode Instruction.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.doc.comment.support` *Javadoc Comment Support.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.overridingPackageDefaultMethod` *Reporting Attempt to Override Package Visible Method.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.methodWithConstructorName` *Reporting Method With Constructor Name.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.deprecation` *Reporting Deprecation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.terminalDeprecation` *Reporting Terminal Deprecation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.deprecationInDeprecatedCode` *Reporting Deprecation Inside Deprecated Code.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.deprecationWhenOverridingDeprecatedMethod` *Reporting Deprecation When Overriding Deprecated Method.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.hiddenCatchBlock` *Reporting Hidden Catch Block.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedLocal` *Reporting Unused Local.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedParameter` *Reporting Unused Parameter.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedExceptionParameter` *Reporting Unused Exception Parameter.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedParameterWhenImplementingAbstract` *Reporting Unused Parameter if Implementing Abstract Method.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unusedParameterWhenOverridingConcrete` *Reporting Unused Parameter if Overriding Concrete Method.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unusedParameterIncludeDocCommentReference` *Consider Reference in Doc Comment for Unused Parameter Check.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unusedImport` *Reporting Unused Import.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedTypeArgumentsForMethodInvocation` *Reporting Presence of Type Arguments for a Non-Generic Method Invocation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.syntheticAccessEmulation` *Reporting Synthetic Access Emulation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedTypeParameter` *Reporting Unused Type Parameter.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.nonExternalizedStringLiteral` *Reporting Non-Externalized String Literal.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.assertIdentifier` *Reporting Usage of <code>assert</code> Identifier.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.enumIdentifier` *Reporting Usage of <code>enum</code> Identifier.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.staticAccessReceiver` *Reporting Non-Static Reference to a Static Member.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.indirectStaticAccess` *Reporting Indirect Reference to a Static Member.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.noEffectAssignment` *Reporting Assignment with no Effect.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.incompatibleNonInheritedInterfaceMethod` *Reporting Interface Method not Compatible with non-Inherited Methods.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedPrivateMember` *Reporting Unused Private Members.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.localVariableHiding` *Reporting Local Variable Declaration Hiding another Variable.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.specialParameterHidingField` *Reporting Special Parameter Hiding another Field.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.fieldHiding` *Reporting Field Declaration Hiding another Variable.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.typeParameterHiding` *Reporting Type Declaration Hiding another Type.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.possibleAccidentalBooleanAssignment` *Reporting Possible Accidental Boolean Assignment.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.fallthroughCase` *Reporting Switch Fall-Through Case.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.emptyStatement` *Reporting Empty Statements and Unnecessary Semicolons.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.booleanMethodThrowingException` ** `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unnecessaryTypeCheck` *Reporting Unnecessary Type Check.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unnecessaryElse` *Reporting Unnecessary Else.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.undocumentedEmptyBlock` *Reporting Undocumented Empty Block.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.finallyBlockNotCompletingNormally` *Reporting Finally Blocks Not Completing Normally.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedDeclaredThrownException` *Reporting Unused Declared Thrown Exception.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedDeclaredThrownExceptionWhenOverriding` *Reporting Unused Declared Thrown Exception in Overriding Method.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unusedDeclaredThrownExceptionIncludeDocCommentReference` *Consider Reference in Doc Comment for Unused Declared Thrown Exception Check.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unusedDeclaredThrownExceptionExemptExceptionAndThrowable` *Reporting Unused Declared Thrown Exception Exempts Exception And Throwable.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unqualifiedFieldAccess` *Reporting Unqualified Access to Field.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.uncheckedTypeOperation` *Reporting Unchecked Type Operation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.rawTypeReference` *Reporting Raw Type Reference.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unavoidableGenericTypeProblems` *Reporting of Unavoidable Generic Type Problems due to raw APIs.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.finalParameterBound` *Reporting final Bound for Type Parameter.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingSerialVersion` *Reporting Missing Declaration of serialVersionUID Field on Serializable Class.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.varargsArgumentNeedCast` *Reporting Varargs Argument Needing a Cast in Method/Constructor Invocation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.autoboxing` *Reporting Boxing/Unboxing Conversion.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.annotationSuperInterface` *Reporting Use of Annotation Type as Super Interface.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingOverrideAnnotation` *Reporting Missing <code>@Override</code> Annotation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingOverrideAnnotationForInterfaceMethodImplementation` *Reporting Missing <code>@Override</code> Annotation for interface method implementation.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.missingDeprecatedAnnotation` *Reporting Missing <code>@Deprecated</code> Annotation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingHashCodeMethod` *Reporting Missing HashCode Method.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.deadCode` *Reporting Dead Code.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.deadCodeInTrivialIfStatement` *Reporting Dead Code Inside Trivial If Statement.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.incompleteEnumSwitch` *Reporting Incomplete Enum Switch.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingEnumCaseDespiteDefault` *Reporting Missing Enum Case In Switch Despite An Existing Default Case.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.missingDefaultCase` *Reporting Missing Default Case In Switch.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedLabel` *Reporting Unreferenced Label.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.invalidJavadoc` *Reporting Invalid Javadoc Comment.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.invalidJavadocTags` *Reporting Invalid Javadoc Tags.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.invalidJavadocTagsDeprecatedRef` *Reporting Invalid Javadoc Tags with Deprecated References.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.invalidJavadocTagsNotVisibleRef` *Reporting Invalid Javadoc Tags with Not Visible References.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.missingJavadocTags` *Reporting Missing Javadoc Tags.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingJavadocTagsOverriding` *Reporting Missing Javadoc Tags on Overriding Methods.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.missingJavadocTagsMethodTypeParameters` *Reporting Missing Javadoc Tags for Method Type Parameters.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.missingJavadocComments` *Reporting Missing Javadoc Comments.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingJavadocCommentsOverriding` *Reporting Missing Javadoc Comments on Overriding Methods.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.noImplicitStringConversion` *Reporting Usage of <code>char[]</code> Expressions in String Concatenations.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.fatalOptionalError` *Treating Optional Error as Fatal.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.parameterAssignment` *Reporting Parameter Assignment.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.reportMethodCanBeStatic` *Reporting a method that qualifies as static, but not declared static.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.reportMethodCanBePotentiallyStatic` *Reporting a method that may qualify as static, but not declared static.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unclosedCloseable` *Reporting a resource that is not closed properly.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.potentiallyUnclosedCloseable` *Reporting a resource that may not be closed properly.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.explicitlyClosedAutoCloseable` *Reporting a resource that is not managed by try-with-resources.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unlikelyCollectionMethodArgumentType` *Reporting a method invocation providing an argument of an unlikely type.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unlikelyCollectionMethodArgumentTypeStrict` *Perform strict analysis against the expected type of collection methods.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.annotation.nullanalysis` *Annotation-based Null Analysis.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.annotation.missingNonNullByDefaultAnnotation` *Reporting missing default nullness annotation.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.nullSpecViolation` *Reporting Violations of Null Specifications.* `{  "error", "warning"  }`

`org.eclipse.jdt.core.compiler.problem.nullAnnotationInferenceConflict` *Reporting conflicts between declared null annotation and inferred null value* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.nullUncheckedConversion` *Reporting unchecked conversion from a type with unknown nullness to a null annotated type* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.pessimisticNullAnalysisForFreeTypeVariables` *Reporting problems detected by pessimistic null analysis for free type variables.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.redundantNullAnnotation` *Reporting Redundant Null Annotations.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.syntacticNullAnalysisForFields` *Perform syntactic null analysis for fields.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.annotation.inheritNullAnnotations` *Inheritance of null annotations.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.nonnullParameterAnnotationDropped` *Reporting Dropped Nonnull Parameter Annotations.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.nonnullTypeVariableFromLegacyInvocation` *Reporting Unsafe NonNull Interpretation Of Type Variables.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.annotatedTypeArgumentToUnannotated` *Reporting Unsafe Conversion To Unannotated Type Argument.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.release` *Use system libraries from release.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.taskCaseSensitive` *Determining whether task tags are case-sensitive.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.forbiddenReference` *Reporting Forbidden Reference to Type with Restricted Access.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.discouragedReference` *Reporting Discouraged Reference to Type with Restricted Access.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.suppressWarnings` *Determining Effect of <code>@SuppressWarnings</code>.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.includeNullInfoFromAsserts` *Raise null related errors or warnings arising because of assert statements.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.suppressOptionalErrors` *Further Determining the Effect of <code>@SuppressWarnings</code> if also* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.unhandledWarningToken` *Reporting Unhandled Warning Token for <code>@SuppressWarnings</code>.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedWarningToken` *Reporting Unnecessary <code>@SuppressWarnings</code>.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.nullReference` *Reporting Null Dereference.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.potentialNullReference` *Reporting Potential Null Dereference.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.redundantNullCheck` *Reporting Redundant Null Check.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.overridingMethodWithoutSuperInvocation` *Reporting Overriding method that* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.redundantSuperinterface` *Reporting Redundant Superinterface.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.comparingIdentical` *Reporting Comparison of Identical Expressions.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.missingSynchronizedOnInheritedMethod` *Reporting Missing Synchronized Modifier On Inherited Method.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.unusedObjectAllocation` *Reporting Allocation of an Unused Object.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.redundantSpecificationOfTypeArguments` *Reporting redundant specification of type arguments in class instance creation expressions.* `{  "error", "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.computeJavaBuildOrder` *Computing Project Build Order.* `{  "compute", "ignore"  }`

`org.eclipse.jdt.core.builder.duplicateResourceTask` *Reporting Duplicate Resources.* `{  "error", "warning"  }`

`org.eclipse.jdt.core.builder.cleanOutputFolder` *Cleaning Output Folder(s).* `{  "clean", "ignore"  }`

`org.eclipse.jdt.core.builder.recreateModifiedClassFileInOutputFolder` *Recreate Modified class files in Output Folder.* `{  "enabled", "ignore"  }`

`org.eclipse.jdt.core.incompleteClasspath` *Reporting Incomplete Classpath.* `{  "error", "warning" }`

`org.eclipse.jdt.core.circularClasspath` *Reporting Classpath Cycle.* `{  "error", "warning"  }`

`org.eclipse.jdt.core.incompatibleJDKLevel` *Reporting Incompatible JDK Level for Required Binaries.* `{  "error", "warning", "ignore"  }`

`org.eclipse.jdt.core.builder.invalidClasspath` *Abort if Invalid Classpath.* `{  "abort", "ignore"  }`

`org.eclipse.jdt.core.classpath.exclusionPatterns` *Enabling Usage of Classpath Exclusion Patterns.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.classpath.multipleOutputLocations` *Enabling Usage of Classpath Multiple Output Locations.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.classpath.outputOverlappingAnotherSource` *Reporting an output location overlapping another source location.* `{  "error", "warning", "ignore"  }`

`org.eclipse.jdt.core.classpath.mainOnlyProjectHasTestOnlyDependency` *Reporting if a project which has only main sources depends on a project with only test sources.* `{  "error", "ignore"  }`

`org.eclipse.jdt.core.compiler.problem.enablePreviewFeatures` *Enabling support for preview language features.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.compiler.problem.reportPreviewFeatures` *Reporting Preview features.* `{  "warning", "info", "ignore"  }`

`org.eclipse.jdt.core.codeComplete.visibilityCheck` *Activate Visibility Sensitive Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.deprecationCheck` *Activate Deprecation Sensitive Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.camelCaseMatch` *Activate Camel Case Sensitive Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.subwordMatch` *Activate Subword Code Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.forceImplicitQualification` *Automatic Qualification of Implicit Members.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.forbiddenReferenceCheck` *Activate Forbidden Reference Sensitive Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.discouragedReferenceCheck` *Activate Discouraged Reference Sensitive Completion.* `{ "enabled", "disabled" }`

`org.eclipse.jdt.core.codeComplete.suggestStaticImports` *Activate Suggestion of Static Import.* `{ "enabled", "disabled" }`