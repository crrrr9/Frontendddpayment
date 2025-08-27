package com.scb.payment_initiation.repository;

import com.scb.payment_initiation.entity.User;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

public interface UserRepository extends JpaRepository<User, Long> {
    Optional<User> findByUsername(String username);
    Optional<User> findByEmail(String email);
}
java
Copy code
package com.scb.payment_initiation.repository;

import com.scb.payment_initiation.entity.Role;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

public interface RoleRepository extends JpaRepository<Role, Long> {
    Optional<Role> findByRoleName(String roleName);
}
java
Copy code
package com.scb.payment_initiation.repository;

import com.scb.payment_initiation.entity.UserRole;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.List;

public interface UserRoleRepository extends JpaRepository<UserRole, Long> {
    List<UserRole> findByUser_UserId(Long userId);
    List<UserRole> findByRole_RoleId(Long roleId);
}
