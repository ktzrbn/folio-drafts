# Managing Roles with Eureka

## Overview
The new Eureka platform, which FOLIO is adopting with the Sunflower release, replaces the permission-based access control model with a permission model based on roles. This page
explains how to manage roles and their assignments. Migrating permissions from the Okapi platform to Eureka can be found at the bottom of the page. 

## Terminology 

- Permission 
	- A permission is an object in FOLIO that can be used to control access to FOLIO apps, workflows, and data
	- A permission can have a number of different attributes, depending on whether you are viewing the permission in FOLIO's code or whether you are looking at permissions for a user on a FOLIO tenant
	 
- Permission set
	- A permission with one or more subpermissions 
	- Can be nested infinitely 

- Resource
	- Something in FOLIO on which users can perform operations, e.g. orders, instances, etc.

- Action
	- An operation that manipulates a resource, e.g. create, edit, view, delete, execute, etc.

- Capabilities 
	- Capabilities define the ability to perform an **action** on a FOLIO **resource**, e.g. Edit (action) on Instances (resource)
	- Derived from information in permissions module descriptors 
	- Capabilities are managed by the system. Users and admins cannot create or remove capabilities. Instead, they're created in applications that are enabled for tenants 
	- They maintain a reference to the *permission* from which they were created
	- They maintain a reference to the *application* which provides them 

- Capability sets
	- Capability sets are comprised of **capabilities**
	- Derived from information in module descriptors (Permission sets) 
	- Are managed by the system. Users and admins cannot create or remove capability sets. Instead, they're created in applications that are enabled for tenants
	- Maintain a reference to the *permission* from which they were created
	- Maintain a reference to the *application* which provides them

- Roles
	- Comprised of capabilities and/or capability sets
	- Created/managed by administrators, not the system
	- Cannot be nested. Roles are flat
	- Are reusable 

- Default roles
	- Roles provided by the system, optionally loaded during tenant entitlement 

- Policies 
	- Provides greater control over who can do what, when, and from where. For example, policies could be created to only allow users to perform check-in/check-out operations during normal business hours from certain locations
	- Policies are associated with capabilities 
	- Time-based policies are managed by administrators, not by the system 

- AuthUser
	- Refers to a user record in [Keycloak](https://github.com/folio-org/folio-keycloak)
	- AuthUsers are managed by FOLIO. No direct interaction with Keycloak is required
	- AuthUsers are a subset of Users, which include staff, patrons, administrators, etc. 
	- A user becomes an AuthUser if they are assigned credentials, roles, or capabilities. The Keycloak user record is only needed for those who log in and use FOLIO. There is no need for Keycloak to know about patrons and others who are just data in the system 

**How do these relate to one another?** 
This diagram may help you visualize the relationships between some of these terms: 

![image](/root/folio-drafts/relation-diagram.png)

## Role Creation 

## Role Modification 

## Role Deletion 

## Role Duplication 

## Shared Roles

## Managing Role Assignments 

### Settings / Authorization Roles 

### Users App

## Migration 

### Migration APIs

### Post-migration Cleanup 

## Tips and Tricks 

## Looking Ahead 
